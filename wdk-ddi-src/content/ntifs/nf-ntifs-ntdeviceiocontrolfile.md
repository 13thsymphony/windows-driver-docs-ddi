---
UID: NF.ntifs.NtDeviceIoControlFile
title: NtDeviceIoControlFile
author: windows-driver-content
description: The ZwDeviceIoControlFile routine sends a control code directly to a specified device driver, causing the corresponding driver to perform the specified operation.
old-location: kernel\zwdeviceiocontrolfile.htm
old-project: kernel
ms.assetid: 4dc38fcd-4b87-4c34-8ae2-685bf47e3fde
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: NtDeviceIoControlFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwDeviceIoControlFile,NtDeviceIoControlFile
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
req.iface: 
---

# NtDeviceIoControlFile function



## -description
<p>The <b>ZwDeviceIoControlFile</b> routine sends a control code directly to a specified device driver, causing the corresponding driver to perform the specified operation.</p>


## -syntax

````
NTSTATUS ZwDeviceIoControlFile(
  _In_      HANDLE           FileHandle,
  _In_opt_  HANDLE           Event,
  _In_opt_  PIO_APC_ROUTINE  ApcRoutine,
  _In_opt_  PVOID            ApcContext,
  _Out_     PIO_STATUS_BLOCK IoStatusBlock,
  _In_      ULONG            IoControlCode,
  _In_opt_  PVOID            InputBuffer,
  _In_      ULONG            InputBufferLength,
  _Out_opt_ PVOID            OutputBuffer,
  _In_      ULONG            OutputBufferLength
);
````


## -parameters
<dl>

### -param FileHandle [in]

<dd>
<p>Handle returned by <a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a> or <a href="..\wdm\nf-wdm-zwopenfile.md">ZwOpenFile</a> for the file object representing the device to which the control information should be given or from which information should be returned. The file object must have been opened for asynchronous I/O if the caller specifies an <i>Event</i>, <i>ApcRoutine</i>, and an APC context (in <i>ApcContext</i>), or a completion context (in <i>ApcContext</i>). For I/O to an underlying mass-storage device, the file object must have been opened for Direct Access to Storage Device (DASD) access.</p>
</dd>

### -param Event [in, optional]

<dd>
<p>Handle for a caller-created event. If this parameter is supplied, the caller will be put into a wait state until the requested operation is completed and the given event is set to the Signaled state. This parameter is optional and can be <b>NULL</b>. It must be <b>NULL</b> if the caller will wait for the <i>FileHandle</i> to be set to the Signaled state.</p>
</dd>

### -param ApcRoutine [in, optional]

<dd>
<p>Address of an optional, caller-supplied APC routine to be called when the requested operation completes. This parameter can be <b>NULL</b>. It must be <b>NULL</b> if there is an I/O completion object associated with the file object.</p>
</dd>

### -param ApcContext [in, optional]

<dd>
<p>Pointer to a caller-determined context area. This parameter value is used as the APC context if the caller supplies an APC, or is used as the completion context if an I/O completion object has been associated with the file object. When the operation completes, either the APC context is passed to the APC, if one was specified, or the completion context is included as part of the completion message that the I/O Manager posts to the associated I/O completion object.</p>
<p>This parameter is optional and can be <b>NULL</b>. It must be <b>NULL</b> if <i>ApcRoutine</i> is <b>NULL</b> and there is no I/O completion object associated with the file object.</p>
</dd>

### -param IoStatusBlock [out]

<dd>
<p>Pointer to a variable that receives the final completion status and information about the operation. For successful calls that return data, the number of bytes written to the <i>OutputBuffer</i> is returned in the <b>Information</b> member.</p>
</dd>

### -param IoControlCode [in]

<dd>
<p>IOCTL_<i>XXX</i> code that indicates which device I/O control operation is to be carried out on, usually by the underlying device driver. The value of this parameter determines the format and required length of the <i>InputBuffer</i> and <i>OutputBuffer</i>, as well as which of the following parameter pairs are required. For detailed information about the system-defined, device-type-specific IOCTL_<i>XXX</i> codes, see the <a href="https://msdn.microsoft.com/1ef3e216-1322-42c3-b070-94cddfb2133c">device technology-specific section</a> of the Microsoft Windows Driver Kit (WDK) documentation and <a href="base.device_input_and_output_control_ioctl_">Device Input and Output Control Codes</a> in the Microsoft Windows SDK documentation.</p>
</dd>

### -param InputBuffer [in, optional]

<dd>
<p>Pointer to a caller-allocated input buffer that contains device-specific information to be given to the target device. If <i>IoControlCode</i> specifies an operation that does not require input data, this pointer can be <b>NULL</b>.</p>
</dd>

### -param InputBufferLength [in]

<dd>
<p>Size, in bytes, of the buffer at <i>InputBuffer</i>. If <i>InputBuffer</i> is <b>NULL</b>, set <i>InputBufferLength</i> to zero.</p>
</dd>

### -param OutputBuffer [out, optional]

<dd>
<p>Pointer to a caller-allocated output buffer in which information is returned from the target device. If <i>IoControlCode</i> specifies an operation that does not produce output data, this pointer can be <b>NULL</b>.</p>
</dd>

### -param OutputBufferLength [in]

<dd>
<p>Size, in bytes, of the buffer at <i>OutputBuffer</i>. If <i>OutputBuffer</i> is <b>NULL</b>, set <i>OutputBufferLength</i> to zero.</p>
</dd>
</dl>

## -returns
<p><b>ZwDeviceIoControlFile</b> returns STATUS_SUCCESS if the underlying driver(s) successfully carried out the requested operation. Otherwise, the return value can be an error status code propagated from an underlying driver. Possible error status codes include the following:</p><dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>

## -remarks
<p><b>ZwDeviceIoControlFile</b> provides a consistent view of the input and output data to the system and to kernel-mode drivers, while providing applications and underlying drivers with a device-dependent method of specifying a communications interface.</p>

<p>For more information about system-defined IOCTL_<i>XXX</i> codes, and about defining driver-specific IOCTL_<i>XXX</i> or FSCTL_<i>XXX</i> values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565406">Using I/O Control Codes</a> in the <i>Kernel Mode Architecture Guide</i> and <a href="base.device_input_and_output_control_ioctl_">Device Input and Output Control Codes</a> in the Microsoft Windows SDK documentation.</p>

<p>If the caller opened the file for asynchronous I/O (with neither FILE_SYNCHRONOUS_<i>XXX</i> create/open option set), the specified event, if any, will be set to the signaled state when the device control operation completes. Otherwise, the file object specified by <i>FileHandle</i> will be set to the signaled state. If an <i>ApcRoutine</i> was specified, it is called with the <i>ApcContext</i> and <i>IoStatusBlock</i> pointers.</p>

<p>Minifilters should use <a href="..\fltkernel\nf-fltkernel-fltdeviceiocontrolfile.md">FltDeviceIoControlFile</a> instead of <b>ZwDeviceIoControlFile</b>.</p>

<p>Callers of <b>ZwDeviceIoControlFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://msdn.microsoft.com/0578df31-1467-4bad-ba62-081d61278deb">with special kernel APCs enabled</a>.</p>

<p>For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 2000.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL (see Remarks section)</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.wdm_powerirpddis">PowerIrpDDis</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltdeviceiocontrolfile.md">FltDeviceIoControlFile</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iobuildasynchronousfsdrequest.md">IoBuildAsynchronousFsdRequest</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iobuilddeviceiocontrolrequest.md">IoBuildDeviceIoControlRequest</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iobuildsynchronousfsdrequest.md">IoBuildSynchronousFsdRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565406">Using I/O Control Codes</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwopenfile.md">ZwOpenFile</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwDeviceIoControlFile routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
