---
UID: NF:wdm.IoBuildDeviceIoControlRequest
title: IoBuildDeviceIoControlRequest function
author: windows-driver-content
description: The IoBuildDeviceIoControlRequest routine allocates and sets up an IRP for a synchronously processed device control request.
old-location: kernel\iobuilddeviceiocontrolrequest.htm
old-project: kernel
ms.assetid: dde2a45d-9257-4d94-928a-e25f112b2773
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoBuildDeviceIoControlRequest
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
req.alt-api: IoBuildDeviceIoControlRequest
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: IoAllocateIrpSignalEventInCompletion, IoAllocateIrpSignalEventInCompletion2, IoAllocateIrpSignalEventInCompletion3, IoBuildDeviceControlNoFree, IoBuildDeviceControlWait, IoBuildDeviceControlWaitTimeout, IoBuildDeviceIoControlSetEvent, IrqlIoPassive1, PowerIrpDDis, SignalEventInCompletion, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoBuildDeviceIoControlRequest function



## -description
The <b>IoBuildDeviceIoControlRequest</b> routine allocates and sets up an IRP for a synchronously processed device control request.



## -syntax

````
PIRP IoBuildDeviceIoControlRequest(
  _In_      ULONG            IoControlCode,
  _In_      PDEVICE_OBJECT   DeviceObject,
  _In_opt_  PVOID            InputBuffer,
  _In_      ULONG            InputBufferLength,
  _Out_opt_ PVOID            OutputBuffer,
  _In_      ULONG            OutputBufferLength,
  _In_      BOOLEAN          InternalDeviceIoControl,
  _In_opt_  PKEVENT          Event,
  _Out_     PIO_STATUS_BLOCK IoStatusBlock
);
````


## -parameters

### -param IoControlCode [in]

Supplies the I/O control code (<a href="wdkgloss.i#wdkgloss.ioctl#wdkgloss.ioctl"><i>IOCTL</i></a>) to be used in the request. For information about device type-specific I/O control codes, see device type-specific sections in the Windows Driver Kit (WDK). 


### -param DeviceObject [in]

Supplies a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure for the next-lower driver's device object, which represents the target device.


### -param InputBuffer [in, optional]

Supplies a pointer to an input buffer to be passed to the lower driver, or <b>NULL</b> if the request does not pass input data to lower drivers.


### -param InputBufferLength [in]

Supplies the length, in bytes, of the input buffer. If <i>InputBuffer</i> is <b>NULL</b>, <i>InputBufferLength</i> must be zero.


### -param OutputBuffer [out, optional]

Supplies a pointer to an output buffer in which the lower driver is to return data, or <b>NULL</b> if the request does not require lower drivers to return data.


### -param OutputBufferLength [in]

Supplies the length, in bytes, of the output buffer. If <i>OutputBuffer</i> is <b>NULL</b>, <i>OutputBufferLength</i> must be zero.


### -param InternalDeviceIoControl [in]

If <b>TRUE</b>, the routine sets the IRP's major function code to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>. Otherwise, the routine sets the IRP's major function code to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a>.


### -param Event [in, optional]

Supplies a pointer to a caller-allocated and initialized event object. The I/O manager sets the event to the Signaled state when a lower-level driver completes the requested operation. After calling <a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>, the driver can wait for the event object. The <i>Event</i> parameter is optional and can be set to NULL. However, if <i>Event</i> is NULL, the caller must supply an <a href="..\wdm\nc-wdm-io_completion_routine.md">IoCompletion</a> routine for the IRP to notify the caller when the operation completes.


### -param IoStatusBlock [out]

Specifies an I/O status block to be set when the request is completed by lower drivers.


## -returns
If the operation succeeds, <b>IoBuildDeviceIoControlRequest</b> returns a pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>, with the next-lower driver's I/O stack location set up from the supplied parameters. Otherwise, the routine returns <b>NULL</b>.


## -remarks
A driver can call <b>IoBuildDeviceIoControlRequest</b> to set up IRPs for device control requests that it synchronously sends to lower-level drivers.

After calling <b>IoBuildDeviceIoControlRequest</b> to create a request, the driver must call <a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a> to send the request to the next-lower driver. If <b>IoCallDriver</b> returns STATUS_PENDING, the driver must wait for the completion of the IRP by calling <a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a> on the given <i>Event</i>. Most drivers do not need to set an <a href="..\wdm\nc-wdm-io_completion_routine.md">IoCompletion</a> routine for the IRP.

IRPs that are created by <b>IoBuildDeviceIoControlRequest</b> must be completed by a driver's call to <a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>. A driver that calls <b>IoBuildDeviceIoControlRequest</b> must not call <a href="..\wdm\nf-wdm-iofreeirp.md">IoFreeIrp</a>, because the I/O manager frees these synchronous IRPs after <b>IoCompleteRequest</b> has been called.

<b>IoBuildDeviceIoControlRequest</b> queues the IRPs that it creates to an IRP queue that is specific to the current thread. If the thread exits, the I/O manager cancels the IRP.

If the caller supplies an <i>InputBuffer</i> or <i>OutputBuffer</i> parameter, this parameter must point to a buffer that resides in system memory. The caller is responsible for validating any parameter values that it copies into the input buffer from a user-mode buffer. The input buffer might contain parameter values that are interpreted differently depending on whether the originator of the request is a user-mode application or a kernel-mode driver. In the IRP that <b>IoBuildDeviceIoControlRequest</b> returns, the <b>RequestorMode</b> field is always set to <b>KernelMode</b>. This value indicates that the request, and any information contained in the request, is from a trusted, kernel-mode component.

If the caller cannot validate parameter values that it copies from a user-mode buffer to the input buffer, or if these values must not be interpreted as coming from a kernel-mode component, the caller should set the <b>RequestorMode</b> field in the IRP to <b>UserMode</b>. This setting informs the driver that handles the I/O control request that the buffer contains untrusted, user-mode data.

The actual method by which the contents of the <i>InputBuffer</i> and <i>OutputBuffer</i> parameters are stored in the IRP depends on the <i>TransferType</i> value for the IOCTL. For more information about this value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540663">Buffer Descriptions for I/O Control Codes</a>.


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
&lt;= APC_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh975155">IoAllocateIrpSignalEventInCompletion</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975156">IoAllocateIrpSignalEventInCompletion2</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975157">IoAllocateIrpSignalEventInCompletion3</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975160">IoBuildDeviceControlNoFree</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975161">IoBuildDeviceControlWait</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975162">IoBuildDeviceControlWaitTimeout</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975163">IoBuildDeviceIoControlSetEvent</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff547763">IrqlIoPassive1</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975204">PowerIrpDDis</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975249">SignalEventInCompletion</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh454220">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioallocateirp.md">IoAllocateIrp</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iobuildasynchronousfsdrequest.md">IoBuildAsynchronousFsdRequest</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iobuildsynchronousfsdrequest.md">IoBuildSynchronousFsdRequest</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keinitializeevent.md">KeInitializeEvent</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoBuildDeviceIoControlRequest routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

