---
UID: NF.wdm.ZwReadFile
title: ZwReadFile function
author: windows-driver-content
description: The ZwReadFile routine reads data from an open file.
old-location: kernel\zwreadfile.htm
old-project: kernel
ms.assetid: 0f1ec015-bda6-45fe-973d-be414aece918
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: ZwReadFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwReadFile,NtReadFile
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: PowerIrpDDis, BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctlA, BufAfterReqCompletedReadA, BufAfterReqCompletedWriteA, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# ZwReadFile function



## -description
The <b>ZwReadFile</b> routine reads data from an open file. 



## -syntax

````
NTSTATUS ZwReadFile(
  _In_     HANDLE           FileHandle,
  _In_opt_ HANDLE           Event,
  _In_opt_ PIO_APC_ROUTINE  ApcRoutine,
  _In_opt_ PVOID            ApcContext,
  _Out_    PIO_STATUS_BLOCK IoStatusBlock,
  _Out_    PVOID            Buffer,
  _In_     ULONG            Length,
  _In_opt_ PLARGE_INTEGER   ByteOffset,
  _In_opt_ PULONG           Key
);
````


## -parameters

### -param FileHandle [in]

Handle to the file object. This handle is created by a successful call to <a href="kernel.zwcreatefile">ZwCreateFile</a> or <a href="kernel.zwopenfile">ZwOpenFile</a>. 


### -param Event [in, optional]

Optionally, a handle to an event object to set to the signaled state after the read operation completes. Device and intermediate drivers should set this parameter to <b>NULL</b>.


### -param ApcRoutine [in, optional]

This parameter is reserved. Device and intermediate drivers should set this pointer to <b>NULL</b>.


### -param ApcContext [in, optional]

This parameter is reserved. Device and intermediate drivers should set this pointer to <b>NULL</b>.


### -param IoStatusBlock [out]

Pointer to an <a href="kernel.io_status_block">IO_STATUS_BLOCK</a> structure that receives the final completion status and information about the requested read operation. The <b>Information</b> member receives the number of bytes actually read from the file.


### -param Buffer [out]

Pointer to a caller-allocated buffer that receives the data read from the file.


### -param Length [in]

The size, in bytes, of the buffer pointed to by <i>Buffer</i>.


### -param ByteOffset [in, optional]

Pointer to a variable that specifies the starting byte offset in the file where the read operation will begin. If an attempt is made to read beyond the end of the file, <b>ZwReadFile</b> returns an error.

If the call to <a href="kernel.zwcreatefile">ZwCreateFile</a> set either of the <b>CreateOptions</b> flags FILE_SYNCHRONOUS_IO_ALERT or FILE_SYNCHRONOUS_IO_NONALERT, the I/O Manager maintains the current file position. If so, the caller of <b>ZwReadFile</b> can specify that the current file position offset be used instead of an explicit <b>ByteOffset</b> value. This specification can be made by using one of the following methods:

<ul>
<li>
Specify a pointer to a LARGE_INTEGER value with the <b>HighPart</b> member set to -1 and the <b>LowPart</b> member set to the system-defined value FILE_USE_FILE_POINTER_POSITION.

</li>
<li>
Pass a <b>NULL</b> pointer for <i>ByteOffset</i>.

</li>
</ul>
<b>ZwReadFile</b> updates the current file position by adding the number of bytes read when it completes the read operation, if it is using the current file position maintained by the I/O Manager.

Even when the I/O Manager is maintaining the current file position, the caller can reset this position by passing an explicit <i>ByteOffset</i> value to <b>ZwReadFile</b>. Doing this automatically changes the current file position to that <i>ByteOffset</i> value, performs the read operation, and then updates the position according to the number of bytes actually read. This technique gives the caller atomic seek-and-read service.


### -param Key [in, optional]

Device and intermediate drivers should set this pointer to <b>NULL</b>. 


## -returns
<b>ZwReadFile</b> returns either STATUS_SUCCESS or the appropriate NTSTATUS error code.


## -remarks
Callers of <b>ZwReadFile</b> must have already called <a href="kernel.zwcreatefile">ZwCreateFile</a> with the FILE_READ_DATA or GENERIC_READ value set in the <i>DesiredAccess</i> parameter.

If the preceding call to <a href="kernel.zwcreatefile">ZwCreateFile</a> set the FILE_NO_INTERMEDIATE_BUFFERING flag in the <i>CreateOptions</i> parameter to <b>ZwCreateFile</b>, the <i>Length</i> and <i>ByteOffset</i> parameters to <b>ZwReadFile</b> must be multiples of the sector size. For more information, see <b>ZwCreateFile</b>.

<b>ZwReadFile</b> begins reading from the given <i>ByteOffset</i> or the current file position into the given <i>Buffer</i>. It terminates the read operation under one of the following conditions:

The buffer is full because the number of bytes specified by the <i>Length</i> parameter has been read. Therefore, no more data can be placed into the buffer without an overflow.

The end of file is reached during the read operation, so there is no more data in the file to be transferred into the buffer.

If the caller opened the file with the SYNCHRONIZE flag set in <i>DesiredAccess</i>, the calling thread can synchronize to the completion of the read operation by waiting on the file handle, <i>FileHandle</i>. The handle is signaled each time that an I/O operation that was issued on the handle completes. However, the caller must not wait on a handle that was opened for synchronous file access (FILE_SYNCHRONOUS_IO_NONALERT or FILE_SYNCHRONOUS_IO_ALERT). In this case, <b>ZwReadFile</b> waits on behalf of the caller and does not return until the read operation is complete. The caller can safely wait on the file handle only if all three of the following conditions are met:

The handle was opened for asynchronous access (that is, neither FILE_SYNCHRONOUS_IO_<b>XXX</b> flag was specified). 

The handle is being used for only one I/O operation at a time. 

<b>ZwReadFile</b> returned STATUS_PENDING. 

A driver should call <b>ZwReadFile</b> in the context of the system process if any of the following conditions exist:

The driver created the file handle that it passes to <b>ZwReadFile</b>.

<b>ZwReadFile</b> will notify the driver of I/O completion by means of an event that the driver created.

<b>ZwReadFile</b> will notify the driver of I/O completion by means of  an APC callback routine that the driver passes to <b>ZwReadFile</b>. 

File and event handles are valid only in the process context where the handles are created. Therefore, to avoid security holes, the driver should create any file or event handle that it passes to <b>ZwReadFile</b> in the context of the system process rather than the context of the process that the driver is in.

Likewise, <b>ZwReadFile</b> should be called in the context of the system process if it notifies the driver of I/O completion by means of an APC, because APCs are always fired in the context of the thread that issues the I/O request. If the driver calls <b>ZwReadFile</b> in the context of a process other than the system one, the APC could be delayed indefinitely, or it might not fire at all.

For more information about working with files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565384">Using Files in a Driver</a>.

Callers of <b>ZwReadFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://msdn.microsoft.com/0578df31-1467-4bad-ba62-081d61278deb">with special kernel APCs enabled</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL (see Remarks section)

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.wdm_powerirpddis">PowerIrpDDis</a>, <a href="devtest.kmdf_bufafterreqcompletedintioctla">BufAfterReqCompletedIntIoctlA</a>, <a href="devtest.kmdf_bufafterreqcompletedioctla">BufAfterReqCompletedIoctlA</a>, <a href="devtest.kmdf_bufafterreqcompletedreada">BufAfterReqCompletedReadA</a>, <a href="devtest.kmdf_bufafterreqcompletedwritea">BufAfterReqCompletedWriteA</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.keinitializeevent">KeInitializeEvent</a>
</dt>
<dt>
<a href="kernel.zwcreatefile">ZwCreateFile</a>
</dt>
<dt>
<a href="kernel.zwqueryinformationfile">ZwQueryInformationFile</a>
</dt>
<dt>
<a href="kernel.zwsetinformationfile">ZwSetInformationFile</a>
</dt>
<dt>
<a href="kernel.zwwritefile">ZwWriteFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwReadFile routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

