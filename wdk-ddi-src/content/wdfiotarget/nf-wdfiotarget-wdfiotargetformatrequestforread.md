---
UID: NF.wdfiotarget.WdfIoTargetFormatRequestForRead
title: WdfIoTargetFormatRequestForRead
author: windows-driver-content
description: The WdfIoTargetFormatRequestForRead method builds a read request for an I/O target but does not send the request.
old-location: wdf\wdfiotargetformatrequestforread.htm
old-project: wdf
ms.assetid: e7c770de-0508-46e8-9820-aee6716fb7a7
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: WdfIoTargetFormatRequestForRead
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfIoTargetFormatRequestForRead
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, RequestFormattedValid, RequestSendAndForgetNoFormatting, RequestSendAndForgetNoFormatting2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# WdfIoTargetFormatRequestForRead function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WdfIoTargetFormatRequestForRead</b> method builds a read request for an I/O target but does not send the request.</p>


## -syntax

````
NTSTATUS WdfIoTargetFormatRequestForRead(
  _In_     WDFIOTARGET       IoTarget,
  _In_     WDFREQUEST        Request,
  _In_opt_ WDFMEMORY         OutputBuffer,
  _In_opt_ PWDFMEMORY_OFFSET OutputBufferOffset,
  _In_opt_ PLONGLONG         DeviceOffset
);
````


## -parameters
<dl>

### -param <i>IoTarget</i> [in]

<dd>
<p>A handle to a local or remote I/O target object that was obtained from a previous call to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a> or <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>, or from a method that a specialized I/O target supplies.</p>
</dd>

### -param <i>Request</i> [in]

<dd>
<p>A handle to a framework request object. For more information, see the following Remarks section.</p>
</dd>

### -param <i>OutputBuffer</i> [in, optional]

<dd>
<p>A handle to a framework memory object. This object represents a buffer that will receive data from the I/O target. This parameter is optional and can be <b>NULL</b>. For more information about this parameter, see the following Remarks section.</p>
</dd>

### -param <i>OutputBufferOffset</i> [in, optional]

<dd>
<p>A pointer to a caller-allocated <a href="..\wudfddi_types\ns-wudfddi-types--wdfmemory-offset.md">WDFMEMORY_OFFSET</a> structure that supplies optional byte offset and length values. The framework uses these values to determine the beginning address and length, within the output buffer, for the data transfer. If this pointer is <b>NULL</b>, the data transfer begins at the beginning of the output buffer, and the transfer size is the buffer size.</p>
</dd>

### -param <i>DeviceOffset</i> [in, optional]

<dd>
<p>A pointer to a variable that specifies a starting offset for the transfer. The I/O target (that is, the next-lower driver) defines how to use this value. For example, the drivers in a disk's driver stack might specify an offset from the beginning of the disk. The I/O target obtains this information in the <b>Parameters.Read.DeviceOffset</b> member of the request's <a href="..\wdfrequest\ns-wdfrequest--wdf-request-parameters.md">WDF_REQUEST_PARAMETERS</a> structure. This pointer is optional. Most drivers set this pointer to <b>NULL</b>.</p>
</dd>
</dl>

## -returns
<p><b>WdfIoTargetFormatRequestForRead</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>An invalid parameter was detected.</p><dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl><p>The transfer length was larger than the buffer length, or the I/O request was already queued to an I/O target.</p><dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><p>The framework could not allocate system resources (typically memory).</p><dl>
<dt><b>STATUS_REQUEST_NOT_ACCEPTED</b></dt>
</dl><p>The I/O request packet (<a href="..\ntifs\ns-ntifs--irp.md">IRP</a>) that the <i>Request</i> parameter represents does not provide enough <a href="..\wdm\ns-wdm--io-stack-location.md">IO_STACK_LOCATION</a> structures to allow the driver to forward the request.</p>

<p> </p>

<p>This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.</p>

<p>A bug check occurs if the driver supplies an invalid object handle.

</p>

## -remarks
<p>Use the <b>WdfIoTargetFormatRequestForRead</b> method, followed by the <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a> method, to send read requests either synchronously or asynchronously. Alternatively, use the <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendreadsynchronously.md">WdfIoTargetSendReadSynchronously</a> method to send read requests synchronously. </p>

<p>You can forward an I/O request that your driver received in an I/O queue, or you can create and send a new request. In either case, the framework requires a request object and some buffer space.</p>

<p>To forward an I/O request that your driver received in an I/O queue:</p>

<p>Specify the received request's handle for the <b>WdfIoTargetFormatRequestForRead</b> method's <i>Request</i> parameter.</p>

<p>Use the received request's output buffer for the <b>WdfIoTargetFormatRequestForRead</b> method's <i>OutputBuffer</i> parameter.</p>

<p>The driver must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a> to obtain a handle to a framework memory object that represents the request's output buffer and must use that handle as the value for <i>OutputBuffer</i>.</p>

<p>For more information about forwarding an I/O request, see <a href="wdf.forwarding_i_o_requests">Forwarding I/O Requests</a>.</p>

<p>Drivers often divide received I/O requests into smaller requests that they send to an I/O target, so your driver might create new requests.</p>

<p>To create a new I/O request:</p>

<p>Create a new request object and supply its handle for the <b>WdfIoTargetFormatRequestForRead</b> method's <i>Request</i> parameter.</p>

<p>Call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a> to preallocate one or more request objects. You can reuse these request objects by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>. Your driver's <a href="..\wdfdriver\nc-wdfdriver-evt-wdf-driver-device-add.md">EvtDriverDeviceAdd</a> callback function can preallocate request objects for a device.</p>

<p>Provide buffer space, and supply the buffer's handle for the <b>WdfIoTargetFormatRequestForRead</b> method's <i>OutputBuffer</i> parameter. </p>

<p>Your driver must specify this buffer space as a WDFMEMORY handle to framework-managed memory. Your driver can do either of the following:</p>

<p>Note that if your driver calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a> and passes the memory handle to <b>WdfIoTargetFormatRequestForRead</b>, the driver must not complete the received I/O request until after the driver deletes, reuses, or reformats the new, driver-created request object. (<b>WdfIoTargetFormatRequestForRead</b> increments the memory object's reference count. Deleting, reusing, or reformatting a request object decrements the memory object's reference count.)</p>

<p>Some I/O targets accept read requests that have a zero-length buffer. For such I/O targets, your driver can specify <b>NULL</b> for the <i>OutputBuffer</i> parameter.</p>

<p>After a driver calls <b>WdfIoTargetFormatRequestForRead</b> to format an I/O request, it must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a> to send the request (either synchronously or asynchronously) to an I/O target.</p>

<p>Multiple calls to <b>WdfIoTargetFormatRequestForRead</b> that use the same request do not cause additional resource allocations. Therefore, to reduce the chance that <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a> will return STATUS_INSUFFICIENT_RESOURCES, your driver's <a href="..\wdfdriver\nc-wdfdriver-evt-wdf-driver-device-add.md">EvtDriverDeviceAdd</a> callback function can call <b>WdfRequestCreate</b> to preallocate one or more request objects for a device. The driver can subsequently reuse (call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>), reformat (call <b>WdfIoTargetFormatRequestForRead</b>), and resend (call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>) each request object without risking a STATUS_INSUFFICIENT_RESOURCES return value from a later call to <b>WdfRequestCreate</b>. All subsequent calls to <b>WdfIoTargetFormatRequestForRead</b> for the reused request object will return STATUS_SUCCESS, if parameter values do not change. (If the driver does not call the same request-formatting method each time, additional resources might be allocated.)</p>

<p>For information about obtaining status information after an I/O request completes, see <a href="wdf.completing_i_o_requests#obtaining_completion_information#obtaining_completion_information">Obtaining Completion Information</a>.</p>

<p>For more information about <b>WdfIoTargetFormatRequestForRead</b>, see <a href="wdf.sending_i_o_requests_to_general_i_o_targets">Sending I/O Requests to General I/O Targets</a>.</p>

<p>For more information about I/O targets, see <a href="wdf.using_i_o_targets">Using I/O Targets</a>.</p>

<p>The following code example creates a framework memory object for a read request's output buffer, formats the read request, registers a <a href="..\wdfrequest\nc-wdfrequest-evt-wdf-request-completion-routine.md">CompletionRoutine</a> callback function, and sends the read request to an I/O target.</p>

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
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdfiotarget.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;=DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>, <a href="devtest.kmdf_requestformattedvalid">RequestFormattedValid</a>, <a href="devtest.kmdf_requestsendandforgetnoformatting">RequestSendAndForgetNoFormatting</a>, <a href="devtest.kmdf_requestsendandforgetnoformatting2">RequestSendAndForgetNoFormatting2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfdriver\nc-wdfdriver-evt-wdf-driver-device-add.md">EvtDriverDeviceAdd</a>
</dt>
<dt>
<a href="..\wdfrequest\ns-wdfrequest--wdf-request-parameters.md">WDF_REQUEST_PARAMETERS</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a>
</dt>
<dt>
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>
</dt>
<dt>
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetformatrequestforwrite.md">WdfIoTargetFormatRequestForWrite</a>
</dt>
<dt>
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendreadsynchronously.md">WdfIoTargetSendReadSynchronously</a>
</dt>
<dt>
<a href="..\wudfddi_types\ns-wudfddi-types--wdfmemory-offset.md">WDFMEMORY_OFFSET</a>
</dt>
<dt>
<a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreate.md">WdfMemoryCreate</a>
</dt>
<dt>
<a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreatepreallocated.md">WdfMemoryCreatePreallocated</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoTargetFormatRequestForRead method%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
