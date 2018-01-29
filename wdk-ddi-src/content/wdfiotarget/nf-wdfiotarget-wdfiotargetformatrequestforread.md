---
UID : NF:wdfiotarget.WdfIoTargetFormatRequestForRead
title : WdfIoTargetFormatRequestForRead function
author : windows-driver-content
description : The WdfIoTargetFormatRequestForRead method builds a read request for an I/O target but does not send the request.
old-location : wdf\wdfiotargetformatrequestforread.htm
old-project : wdf
ms.assetid : e7c770de-0508-46e8-9820-aee6716fb7a7
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : kmdf.wdfiotargetformatrequestforread, WdfIoTargetFormatRequestForRead method, wdf.wdfiotargetformatrequestforread, PFN_WDFIOTARGETFORMATREQUESTFORREAD, DFIOTargetRef_397cd31e-d4d8-40b5-ae7b-5f8e9ed62300.xml, wdfiotarget/WdfIoTargetFormatRequestForRead, WdfIoTargetFormatRequestForRead
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfiotarget.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2, RequestFormattedValid, RequestSendAndForgetNoFormatting, RequestSendAndForgetNoFormatting2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll : 
req.irql : "<=DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWDF_IO_TARGET_STATE, WDF_IO_TARGET_STATE"
req.product : Windows 10 or later.
---


# WdfIoTargetFormatRequestForRead function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoTargetFormatRequestForRead</b> method builds a read request for an I/O target but does not send the request.

## Syntax

````
NTSTATUS WdfIoTargetFormatRequestForRead(
  _In_     WDFIOTARGET       IoTarget,
  _In_     WDFREQUEST        Request,
  _In_opt_ WDFMEMORY         OutputBuffer,
  _In_opt_ PWDFMEMORY_OFFSET OutputBufferOffset,
  _In_opt_ PLONGLONG         DeviceOffset
);
````

## Parameters

`IoTarget`

A handle to a local or remote I/O target object that was obtained from a previous call to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a> or <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>, or from a method that a specialized I/O target supplies.

`Request`

A handle to a framework request object. For more information, see the following Remarks section.

`OutputBuffer`

A handle to a framework memory object. This object represents a buffer that will receive data from the I/O target. This parameter is optional and can be <b>NULL</b>. For more information about this parameter, see the following Remarks section.

`OutputBufferOffset`

A pointer to a caller-allocated <a href="..\wudfddi_types\ns-wudfddi_types-_wdfmemory_offset.md">WDFMEMORY_OFFSET</a> structure that supplies optional byte offset and length values. The framework uses these values to determine the beginning address and length, within the output buffer, for the data transfer. If this pointer is <b>NULL</b>, the data transfer begins at the beginning of the output buffer, and the transfer size is the buffer size.

`DeviceOffset`

A pointer to a variable that specifies a starting offset for the transfer. The I/O target (that is, the next-lower driver) defines how to use this value. For example, the drivers in a disk's driver stack might specify an offset from the beginning of the disk. The I/O target obtains this information in the <b>Parameters.Read.DeviceOffset</b> member of the request's <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_parameters.md">WDF_REQUEST_PARAMETERS</a> structure. This pointer is optional. Most drivers set this pointer to <b>NULL</b>.


## Return Value

<b>WdfIoTargetFormatRequestForRead</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The transfer length was larger than the buffer length, or the I/O request was already queued to an I/O target.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The framework could not allocate system resources (typically memory).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REQUEST_NOT_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
The I/O request packet (<a href="..\wdm\ns-wdm-_irp.md">IRP</a>) that the <i>Request</i> parameter represents does not provide enough <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structures to allow the driver to forward the request.

</td>
</tr>
</table> 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

Use the <b>WdfIoTargetFormatRequestForRead</b> method, followed by the <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a> method, to send read requests either synchronously or asynchronously. Alternatively, use the <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendreadsynchronously.md">WdfIoTargetSendReadSynchronously</a> method to send read requests synchronously. 

You can forward an I/O request that your driver received in an I/O queue, or you can create and send a new request. In either case, the framework requires a request object and some buffer space.

To forward an I/O request that your driver received in an I/O queue:
<ol>
<li>
Specify the received request's handle for the <b>WdfIoTargetFormatRequestForRead</b> method's <i>Request</i> parameter.

</li>
<li>
Use the received request's output buffer for the <b>WdfIoTargetFormatRequestForRead</b> method's <i>OutputBuffer</i> parameter.

The driver must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a> to obtain a handle to a framework memory object that represents the request's output buffer and must use that handle as the value for <i>OutputBuffer</i>.

</li>
</ol>For more information about forwarding an I/O request, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/forwarding-i-o-requests">Forwarding I/O Requests</a>.

Drivers often divide received I/O requests into smaller requests that they send to an I/O target, so your driver might create new requests.

To create a new I/O request:
<ol>
<li>
Create a new request object and supply its handle for the <b>WdfIoTargetFormatRequestForRead</b> method's <i>Request</i> parameter.

Call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a> to preallocate one or more request objects. You can reuse these request objects by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>. Your driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function can preallocate request objects for a device.

</li>
<li>
Provide buffer space, and supply the buffer's handle for the <b>WdfIoTargetFormatRequestForRead</b> method's <i>OutputBuffer</i> parameter. 

Your driver must specify this buffer space as a WDFMEMORY handle to framework-managed memory. Your driver can do either of the following:

<ul>
<li> Call <a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreate.md">WdfMemoryCreate</a> or <a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreatepreallocated.md">WdfMemoryCreatePreallocated</a> to create a new memory buffer, if you want the driver to pass a new buffer to the I/O target.  </li>
<li> Call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a> to obtain a handle to the memory object that represents a received I/O request's buffer, if you want the driver to pass that buffer's contents to the I/O target. </li>
</ul>
Note that if your driver calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a> and passes the memory handle to <b>WdfIoTargetFormatRequestForRead</b>, the driver must not complete the received I/O request until after the driver deletes, reuses, or reformats the new, driver-created request object. (<b>WdfIoTargetFormatRequestForRead</b> increments the memory object's reference count. Deleting, reusing, or reformatting a request object decrements the memory object's reference count.)

</li>
</ol>Some I/O targets accept read requests that have a zero-length buffer. For such I/O targets, your driver can specify <b>NULL</b> for the <i>OutputBuffer</i> parameter.

After a driver calls <b>WdfIoTargetFormatRequestForRead</b> to format an I/O request, it must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a> to send the request (either synchronously or asynchronously) to an I/O target.

Multiple calls to <b>WdfIoTargetFormatRequestForRead</b> that use the same request do not cause additional resource allocations. Therefore, to reduce the chance that <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a> will return STATUS_INSUFFICIENT_RESOURCES, your driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function can call <b>WdfRequestCreate</b> to preallocate one or more request objects for a device. The driver can subsequently reuse (call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>), reformat (call <b>WdfIoTargetFormatRequestForRead</b>), and resend (call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>) each request object without risking a STATUS_INSUFFICIENT_RESOURCES return value from a later call to <b>WdfRequestCreate</b>. All subsequent calls to <b>WdfIoTargetFormatRequestForRead</b> for the reused request object will return STATUS_SUCCESS, if parameter values do not change. (If the driver does not call the same request-formatting method each time, additional resources might be allocated.)

For information about obtaining status information after an I/O request completes, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Obtaining Completion Information</a>.

For more information about <b>WdfIoTargetFormatRequestForRead</b>, see <a href="https://msdn.microsoft.com/3fa897f5-2de8-484b-becb-c2de23fb5e8c">Sending I/O Requests to General I/O Targets</a>.

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfiotarget.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2, RequestFormattedValid, RequestSendAndForgetNoFormatting, RequestSendAndForgetNoFormatting2 |

## See Also

<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendreadsynchronously.md">WdfIoTargetSendReadSynchronously</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>

<a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreate.md">WdfMemoryCreate</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a>

<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_parameters.md">WDF_REQUEST_PARAMETERS</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a>

<a href="..\wudfddi_types\ns-wudfddi_types-_wdfmemory_offset.md">WDFMEMORY_OFFSET</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a>

<a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreatepreallocated.md">WdfMemoryCreatePreallocated</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetformatrequestforwrite.md">WdfIoTargetFormatRequestForWrite</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoTargetFormatRequestForRead method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>