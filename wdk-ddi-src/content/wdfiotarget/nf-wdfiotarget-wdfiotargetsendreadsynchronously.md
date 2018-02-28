---
UID: NF:wdfiotarget.WdfIoTargetSendReadSynchronously
title: WdfIoTargetSendReadSynchronously function
author: windows-driver-content
description: The WdfIoTargetSendReadSynchronously method builds a read request and sends it synchronously to an I/O target.
old-location: wdf\wdfiotargetsendreadsynchronously.htm
old-project: wdf
ms.assetid: bc6ceaac-883b-44af-8ac5-20145a5a6af9
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFIOTargetRef_91d200b2-9585-488f-9477-3b6e528e82cc.xml, WdfIoTargetSendReadSynchronously, WdfIoTargetSendReadSynchronously method, kmdf.wdfiotargetsendreadsynchronously, wdf.wdfiotargetsendreadsynchronously, wdfiotarget/WdfIoTargetSendReadSynchronously
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
req.ddi-compliance: DeferredRequestCompleted, DriverCreate, InternalIoctlReqs, IoctlReqs, KmdfIrql, KmdfIrql2, RequestCompleted, RequestCompletedLocal, SyncReqSend, WriteReqs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfIoTargetSendReadSynchronously
product: Windows
targetos: Windows
req.typenames: WDF_IO_TARGET_STATE, *PWDF_IO_TARGET_STATE
req.product: Windows 10 or later.
---


# WdfIoTargetSendReadSynchronously function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoTargetSendReadSynchronously</b> method builds a read request and sends it synchronously to an I/O target.

## Syntax

````
NTSTATUS WdfIoTargetSendReadSynchronously(
  _In_      WDFIOTARGET               IoTarget,
  _In_opt_  WDFREQUEST                Request,
  _In_opt_  PWDF_MEMORY_DESCRIPTOR    OutputBuffer,
  _In_opt_  PLONGLONG                 DeviceOffset,
  _In_opt_  PWDF_REQUEST_SEND_OPTIONS RequestOptions,
  _Out_opt_ PULONG_PTR                BytesRead
);
````

## Parameters

`IoTarget`

A handle to a local or remote I/O target object that was obtained from a previous call to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a> or <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a> or from a method that a specialized I/O target supplies.

`Request`

A handle to a framework request object. This parameter is optional and can be <b>NULL</b>. For more information about this parameter, see the following Remarks section.

`OutputBuffer`

A pointer to a caller-allocated <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure that describes the buffer that will receive data from the device.This parameter is optional and can be <b>NULL</b>. For more information about this parameter, see the following Remarks section.

`DeviceOffset`

A pointer to a location that specifies a starting offset for the transfer. The I/O target (that is, the next-lower driver) defines how to use this value. For example, the drivers in a disk's driver stack might specify an offset from the beginning of the disk. The I/O target obtains this information in the <b>Parameters.Read.DeviceOffset</b> member of the request's <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_parameters.md">WDF_REQUEST_PARAMETERS</a> structure. This pointer is optional. Most drivers set this pointer to <b>NULL</b>.

`RequestOptions`

A pointer to a caller-allocated <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure that specifies options for the read request. This pointer is optional and can be <b>NULL</b>.

`BytesRead`

A pointer to a location that receives the number of bytes read, if the operation succeeds. This pointer is optional and can be <b>NULL</b>.


## Return Value

If the operation succeeds, <b>WdfIoTargetSendReadSynchronously</b> returns after the I/O request completes, and the return value is the request's completion status value. Otherwise, this method might return one of the following values:

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
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The size of the WDF_REQUEST_SEND_OPTIONS structure that the <i>RequestOptions</i> parameter pointed to was incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The I/O request was already queued to an I/O target.

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
<dt><b>STATUS_IO_TIMEOUT</b></dt>
</dl>
</td>
<td width="60%">
The driver supplied a time-out value and the request did not complete within the allotted time.

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

Use the <b>WdfIoTargetSendReadSynchronously</b> method to send read requests synchronously. To send read requests asynchronously, use the <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetformatrequestforread.md">WdfIoTargetFormatRequestForRead</a> method, followed by the <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a> method.

<b>WdfIoTargetSendReadSynchronously</b> does not return until the request has completed, unless the driver supplies a time-out value in the <i>RequestOptions</i> parameter's <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure, or unless an error is detected.

You can forward an I/O request that your driver received in an I/O queue, or you can create and send a new request. In either case, the framework requires a request object and some buffer space.

To forward an I/O request that your driver received in an I/O queue:

<ol>
<li>
Specify the received request's handle for the <i>Request</i> parameter.

</li>
<li>
Use the received request's output buffer for the <b>WdfIoTargetSendReadSynchronously</b> method's <i>OutputBuffer</i> parameter.

The driver must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a> to obtain a handle to a framework memory object that represents the request's output buffer. Then the driver must place that handle in the <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure that the driver supplies for the <i>OutputBuffer</i> parameter.

</li>
</ol>
For more information about forwarding an I/O request, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/forwarding-i-o-requests">Forwarding I/O Requests</a>.

Drivers often divide received I/O requests into smaller requests that they send to an I/O target, so your driver might create new requests.

To create a new I/O request:

<ol>
<li>
Supply a <b>NULL</b> request handle for the <b>WdfIoTargetSendReadSynchronously</b> method's <i>Request</i> parameter, or create a new request object and supply its handle:<ul>
<li>If you supply a <b>NULL</b> request handle, the framework uses an internal request object. This technique is simple to use, but the driver cannot cancel the request.</li>
<li>If you call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a> to create one or more request objects, you can reuse these request objects by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>. This technique enables your driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function to preallocate request objects for a device. Additionally, another driver thread can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcancelsentrequest.md">WdfRequestCancelSentRequest</a> to cancel the request, if necessary.</li>
</ul>


Your driver can specify a non-<b>NULL</b> <i>RequestOptions</i> parameter, whether the driver provides a non-<b>NULL</b> or a <b>NULL</b> <i>Request</i> parameter. You can, for example, use the <i>RequestOptions</i> parameter to specify a time-out value. 

</li>
<li>
Provide buffer space for the <b>WdfIoTargetSendReadSynchronously</b> method's <i>OutputBuffer</i> parameter. 

Your driver can specify this buffer space as a locally allocated buffer, as a WDFMEMORY handle, or as a memory descriptor list (MDL). You can use whichever method is most convenient. 

If necessary, the framework converts the buffer description to one that is correct for the I/O target's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">method for accessing data buffers</a>. 

The following techniques to specify buffer space are available:

<ul>
<li>
Supply a local buffer.

Because <b>WdfIoTargetSendReadSynchronously</b> handles I/O requests synchronously, the driver can create request buffers that are local to the calling routine, as the following code example shows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_MEMORY_DESCRIPTOR  MemoryDescriptor;
MY_BUFFER_TYPE  MyBuffer;
WDF_MEMORY_DESCRIPTOR_INIT_BUFFER(&amp;MemoryDescriptor,
                                  (PVOID) &amp;MyBuffer,
                                  sizeof(MyBuffer));</pre>
</td>
</tr>
</table></span></div>
</li>
<li>
Supply a WDFMEMORY handle.

Call <a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreate.md">WdfMemoryCreate</a> or <a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreatepreallocated.md">WdfMemoryCreatePreallocated</a> to obtain a handle to framework-managed memory, as the following code example shows. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_MEMORY_DESCRIPTOR  MemoryDescriptor;
WDFMEMORY  MemoryHandle = NULL;
status = WdfMemoryCreate(NULL,
                         NonPagedPool,
                         POOL_TAG,
                         MY_BUFFER_SIZE,
                         &amp;MemoryHandle,
                         NULL);
WDF_MEMORY_DESCRIPTOR_INIT_HANDLE(&amp;MemoryDescriptor,
                                  MemoryHandle,
                                  NULL);</pre>
</td>
</tr>
</table></span></div>
Alternatively, the driver can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a> to obtain a handle to a framework memory object that represents a received I/O request's output buffer, if you want the driver to pass that buffer's contents to the I/O target. The driver must not complete the received I/O request until the new request that <b>WdfIoTargetSendReadSynchronously</b> sends to the I/O target has been deleted, reused, or reformatted. (<b>WdfIoTargetSendReadSynchronously</b> increments the memory object's reference count. Deleting, reusing, or reformatting a request object decrements the memory object's reference count.)

</li>
<li>
Supply an MDL.

Drivers can obtain the MDL that is associated with a received I/O request by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputwdmmdl.md">WdfRequestRetrieveOutputWdmMdl</a>.

</li>
</ul>
</li>
</ol>
Some I/O targets accept read requests that have a zero-length buffer. For such I/O targets, your driver can specify <b>NULL</b> for the <i>OutputBuffer</i> parameter.

For information about obtaining status information after an I/O request completes, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Obtaining Completion Information</a>.

For more information about <b>WdfIoTargetSendReadSynchronously</b>, see <a href="https://msdn.microsoft.com/3fa897f5-2de8-484b-becb-c2de23fb5e8c">Sending I/O Requests to General I/O Targets</a>.

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.


#### Examples

The following code example creates a framework memory object, initializes a <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure, and passes the structure to <b>WdfIoTargetSendReadSynchronously</b>. This example specifies <b>NULL</b> for the request object handle, so the framework will create a new request object for the I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_MEMORY_DESCRIPTOR  MemoryDescriptor;
WDFMEMORY  MemoryHandle = NULL;
ULONG_PTR  bytesRead = NULL;

status = WdfMemoryCreate(
                         NULL,
                         NonPagedPool,
                         POOL_TAG,
                         MY_BUFFER_SIZE,
                         &amp;MemoryHandle,
                         NULL
                         );
WDF_MEMORY_DESCRIPTOR_INIT_HANDLE(
                                  &amp;MemoryDescriptor,
                                  MemoryHandle,
                                  NULL
                                  );
status = WdfIoTargetSendReadSynchronously(
                                          ioTarget,
                                          NULL,
                                          &amp;MemoryDescriptor,
                                          NULL,
                                          NULL,
                                          &amp;bytesRead
                                          );
 </pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfiotarget.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | DeferredRequestCompleted, DriverCreate, InternalIoctlReqs, IoctlReqs, KmdfIrql, KmdfIrql2, RequestCompleted, RequestCompletedLocal, SyncReqSend, WriteReqs |

## See Also

<a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreatepreallocated.md">WdfMemoryCreatePreallocated</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a>



<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_parameters.md">WDF_REQUEST_PARAMETERS</a>



<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>



<a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreate.md">WdfMemoryCreate</a>



<a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcancelsentrequest.md">WdfRequestCancelSentRequest</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendwritesynchronously.md">WdfIoTargetSendWriteSynchronously</a>



<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a>



<a href="..\wdfmemory\nf-wdfmemory-wdf_memory_descriptor_init_handle.md">WDF_MEMORY_DESCRIPTOR_INIT_HANDLE</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetformatrequestforread.md">WdfIoTargetFormatRequestForRead</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputwdmmdl.md">WdfRequestRetrieveOutputWdmMdl</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoTargetSendReadSynchronously method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>