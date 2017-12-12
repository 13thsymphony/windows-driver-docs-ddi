---
UID: NF.wdfiotarget.WdfIoTargetFormatRequestForInternalIoctl
title: WdfIoTargetFormatRequestForInternalIoctl function
author: windows-driver-content
description: The WdfIoTargetFormatRequestForInternalIoctl method builds an internal device control request for an I/O target but does not send the request.
old-location: wdf\wdfiotargetformatrequestforinternalioctl.htm
old-project: wdf
ms.assetid: 201ba120-9f64-4b69-87f0-a368b2e0344d
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: WdfIoTargetFormatRequestForInternalIoctl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfIoTargetFormatRequestForInternalIoctl
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, RequestFormattedValid, RequestSendAndForgetNoFormatting, RequestSendAndForgetNoFormatting2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# WdfIoTargetFormatRequestForInternalIoctl function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoTargetFormatRequestForInternalIoctl</b> method builds an internal device control request for an I/O target but does not send the request.



## -syntax

````
NTSTATUS WdfIoTargetFormatRequestForInternalIoctl(
  _In_     WDFIOTARGET       IoTarget,
  _In_     WDFREQUEST        Request,
  _In_     ULONG             IoctlCode,
  _In_opt_ WDFMEMORY         InputBuffer,
  _In_opt_ PWDFMEMORY_OFFSET InputBufferOffset,
  _In_opt_ WDFMEMORY         OutputBuffer,
  _In_opt_ PWDFMEMORY_OFFSET OutputBufferOffset
);
````


## -parameters

### -param IoTarget [in]

A handle to a local or remote I/O target object that was obtained from a previous call to <a href="wdf.wdfdevicegetiotarget">WdfDeviceGetIoTarget</a> or <a href="wdf.wdfiotargetcreate">WdfIoTargetCreate</a>, or from a method that a specialized I/O target supplies.


### -param Request [in]

A handle to a framework request object. For more information, see the following Remarks section.


### -param IoctlCode [in]

An I/O control code (IOCTL) that the I/O target supports. 


### -param InputBuffer [in, optional]

A handle to a framework memory object. This object represents a buffer that contains data that will be sent to the I/O target. For more information, see the following Remarks section.


### -param InputBufferOffset [in, optional]

A pointer to a caller-allocated <a href="wdf.wdfmemory_offset">WDFMEMORY_OFFSET</a> structure that supplies optional byte offset and length values. The framework uses these values to determine the beginning address and length, within the input buffer, for the data transfer. If this pointer is <b>NULL</b>, the data transfer begins at the beginning of the input buffer, and the transfer size is the buffer size.


### -param OutputBuffer [in, optional]

A handle to a framework memory object. This object represents a buffer that will receive data from the I/O target. For more information, see the following Remarks section.


### -param OutputBufferOffset [in, optional]

A pointer to a caller-allocated <a href="wdf.wdfmemory_offset">WDFMEMORY_OFFSET</a> structure that supplies optional byte offset and length values. The framework uses these values to determine the beginning address and length, within the output buffer, for the data transfer. If this pointer is <b>NULL</b>, the data transfer begins at the beginning of the output buffer, and the transfer size is the buffer size.


## -returns
<b>WdfIoTargetFormatRequestForInternalIoctl</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was detected.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The transfer length was larger than the buffer length, or the I/O request was already queued to an I/O target.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The framework could not allocate system resources (typically memory).
<dl>
<dt><b>STATUS_REQUEST_NOT_ACCEPTED</b></dt>
</dl>The I/O request packet (<a href="kernel.irp">IRP</a>) that the <i>Request</i> parameter represents does not provide enough <a href="kernel.io_stack_location">IO_STACK_LOCATION</a> structures to allow the driver to forward the request.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
Use the <b>WdfIoTargetFormatRequestForInternalIoctl</b> method, followed by the <a href="wdf.wdfrequestsend">WdfRequestSend</a> method, to send internal device control requests either synchronously or asynchronously. Alternatively, use the <a href="wdf.wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a> method to send internal device control requests synchronously. 

For more information about internal device control requests, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565406">Using I/O Control Codes</a>.

You can forward an internal device control request that your driver received in an I/O queue, or you can create and send a new request. In either case, the framework requires a request object and some buffer space.

To forward an internal device control request that your driver received in an I/O queue:

Specify the received request's handle for the <b>WdfIoTargetFormatRequestForInternalIoctl</b> method's <i>Request</i> parameter.

Use the received request's input buffer for the <b>WdfIoTargetFormatRequestForInternalIoctl</b> method's <i>InputBuffer</i> parameter.

The driver must call <a href="wdf.wdfrequestretrieveinputmemory">WdfRequestRetrieveInputMemory</a> to obtain a handle to the request's input buffer, and it must use that handle as the value for <i>InputBuffer</i>.

Use the received request's output buffer for the <b>WdfIoTargetFormatRequestForInternalIoctl</b> method's <i>OutputBuffer</i> parameter.

The driver must call <a href="wdf.wdfrequestretrieveoutputmemory">WdfRequestRetrieveOutputMemory</a> to obtain a handle to the request's output buffer, and it must use that handle as the value for <i>OutputBuffer</i>.

For more information about forwarding an I/O request, see <a href="wdf.forwarding_i_o_requests">Forwarding I/O Requests</a>.

Drivers often divide received I/O requests into smaller requests that they send to an I/O target, so your driver might create new requests.

To create a new I/O request:

Create a new request object and supply its handle for the <b>WdfIoTargetFormatRequestForInternalIoctl</b> method's <i>Request</i> parameter.

Call <a href="wdf.wdfrequestcreate">WdfRequestCreate</a> to preallocate one or more request objects. You can reuse these request objects by calling <a href="wdf.wdfrequestreuse">WdfRequestReuse</a>. Your driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function can preallocate request objects for a device.

Provide buffer space, and supply the buffer's handle for the <b>WdfIoTargetFormatRequestForInternalIoctl</b> method's <i>InputBuffer</i> and <i>OutputBuffer</i> parameters.

Your driver must specify this buffer space as WDFMEMORY handles to framework-managed memory. Your driver can do either of the following:

Note that if your driver calls <a href="wdf.wdfrequestretrieveinputmemory">WdfRequestRetrieveInputMemory</a> or <a href="wdf.wdfrequestretrieveoutputmemory">WdfRequestRetrieveOutputMemory</a> and passes the memory handle to <b>WdfIoTargetFormatRequestForInternalIoctl</b>, the driver must not complete the received I/O request until after the driver deletes, reuses, or reformats the new, driver-created request object. (<b>WdfIoTargetFormatRequestForInternalIoctl</b> increments the memory object's reference count. Deleting, reusing, or reformatting a request object decrements the memory object's reference count.)

After a driver calls <b>WdfIoTargetFormatRequestForInternalIoctl</b> to format a device control request, the driver must call <a href="wdf.wdfrequestsend">WdfRequestSend</a> to send the request (either synchronously or asynchronously) to an I/O target.

Multiple calls to <b>WdfIoTargetFormatRequestForInternalIoctl</b> that use the same request do not cause additional resource allocations. Therefore, to reduce the chance that <a href="wdf.wdfrequestcreate">WdfRequestCreate</a> will return STATUS_INSUFFICIENT_RESOURCES, your driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function can call <b>WdfRequestCreate</b> to preallocate one or more request objects for a device. The driver can subsequently reuse (call <a href="wdf.wdfrequestreuse">WdfRequestReuse</a>), reformat (call <b>WdfIoTargetFormatRequestForInternalIoctl</b>), and resend (call <a href="wdf.wdfrequestsend">WdfRequestSend</a>) each request object without risking a STATUS_INSUFFICIENT_RESOURCES return value from a later call to <b>WdfRequestCreate</b>. All subsequent calls to <b>WdfIoTargetFormatRequestForInternalIoctl</b> for the reused request object will return STATUS_SUCCESS, if parameter values do not change. (However, if the driver does not call the same request-formatting method each time, additional resources might be allocated. Additionally, if the <a href="https://msdn.microsoft.com/967b0199-e9a0-4c8d-9130-c81436c59ca3">I/O control code</a> specifies a transfer type of METHOD_BUFFERED, the framework must allocate a system buffer for each request, and that allocation could fail because of insufficient memory resources.)

For information about obtaining status information after an I/O request completes, see <a href="wdf.completing_i_o_requests#obtaining_completion_information#obtaining_completion_information">Obtaining Completion Information</a>.

For more information about <b>WdfIoTargetFormatRequestForInternalIoctl</b>, see <a href="wdf.sending_i_o_requests_to_general_i_o_targets">Sending I/O Requests to General I/O Targets</a>.

For more information about I/O targets, see <a href="wdf.using_i_o_targets">Using I/O Targets</a>.

The following code example creates a framework memory object that is a child of a request object. Next, the example obtains the buffer that the memory object contains and initializes the buffer. Then, the example formats the request, sets a <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function, and sends the request to an I/O target.


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
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfiotarget.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="wdf.framework_library_versioning">Framework Library Versioning</a>.)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>, <a href="devtest.kmdf_requestformattedvalid">RequestFormattedValid</a>, <a href="devtest.kmdf_requestsendandforgetnoformatting">RequestSendAndForgetNoFormatting</a>, <a href="devtest.kmdf_requestsendandforgetnoformatting2">RequestSendAndForgetNoFormatting2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>
</dt>
<dt>
<a href="wdf.wdfdevicegetiotarget">WdfDeviceGetIoTarget</a>
</dt>
<dt>
<a href="wdf.wdfiotargetcreate">WdfIoTargetCreate</a>
</dt>
<dt>
<a href="wdf.wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>
</dt>
<dt>
<a href="wdf.wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
</dt>
<dt>
<a href="wdf.wdfiotargetformatrequestforioctl">WdfIoTargetFormatRequestForIoctl</a>
</dt>
<dt>
<a href="wdf.wdfmemorycreate">WdfMemoryCreate</a>
</dt>
<dt>
<a href="wdf.wdfmemorycreatepreallocated">WdfMemoryCreatePreallocated</a>
</dt>
<dt>
<a href="wdf.wdfrequestcreate">WdfRequestCreate</a>
</dt>
<dt>
<a href="wdf.wdfrequestretrieveinputmemory">WdfRequestRetrieveInputMemory</a>
</dt>
<dt>
<a href="wdf.wdfrequestretrieveoutputmemory">WdfRequestRetrieveOutputMemory</a>
</dt>
<dt>
<a href="wdf.wdfrequestreuse">WdfRequestReuse</a>
</dt>
<dt>
<a href="wdf.wdfrequestsend">WdfRequestSend</a>
</dt>
<dt>
<a href="wdf.wdfmemory_offset">WDFMEMORY_OFFSET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoTargetFormatRequestForInternalIoctl method%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

