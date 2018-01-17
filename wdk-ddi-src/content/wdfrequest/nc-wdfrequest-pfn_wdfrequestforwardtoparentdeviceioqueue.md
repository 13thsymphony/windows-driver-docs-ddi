---
UID: NC:wdfrequest.PFN_WDFREQUESTFORWARDTOPARENTDEVICEIOQUEUE
title: PFN_WDFREQUESTFORWARDTOPARENTDEVICEIOQUEUE function
author: windows-driver-content
description: The WdfRequestForwardToParentDeviceIoQueue method requeues an I/O request from a child device's I/O queue to a specified I/O queue of the child's parent device.
old-location: wdf\wdfrequestforwardtoparentdeviceioqueue.htm
old-project: wdf
ms.assetid: 81511d81-206c-420b-a956-42cf68b57fc4
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFREQUESTFORWARDTOPARENTDEVICEIOQUEUE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
req.umdf-ver: 
req.alt-api: WdfRequestForwardToParentDeviceIoQueue
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: *PWDF_QUERY_INTERFACE_CONFIG, WDF_QUERY_INTERFACE_CONFIG
req.product: Windows 10 or later.
---

# PFN_WDFREQUESTFORWARDTOPARENTDEVICEIOQUEUE function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfRequestForwardToParentDeviceIoQueue</b> method requeues an I/O request from a child device's I/O queue to a specified I/O queue of the child's parent device.



## -syntax

````
NTSTATUS WdfRequestForwardToParentDeviceIoQueue(
  _In_ WDFREQUEST                   Request,
  _In_ WDFQUEUE                     ParentDeviceQueue,
  _In_ PWDF_REQUEST_FORWARD_OPTIONS ForwardOptions
);
````


## -parameters

### -param Request [in]

A handle to a framework request object.


### -param ParentDeviceQueue [in]

A handle to a framework queue object. 


### -param ForwardOptions [in]

A pointer to a caller-allocated <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_forward_options.md">WDF_REQUEST_FORWARD_OPTIONS</a> structure.


## -returns
<b>WdfRequestForwardToParentDeviceIoQueue</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>The size of the supplied WDF_REQUEST_FORWARD_OPTIONS structure is invalid.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>A member of the supplied WDF_REQUEST_FORWARD_OPTIONS structure contains an invalid value.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>This value is returned if one of the following occurs:

The driver did not obtain the I/O request from an I/O queue.

The source and destination I/O queues are the same.

The specified I/O queue does not belong to the parent device.

The driver has enabled <a href="wdf.guaranteeing_forward_progress_of_i_o_operations">guaranted forward progress</a> and the specified I/O request is reserved for low-memory situations.

The driver did not call <a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitallowforwardingrequesttoparent.md">WdfPdoInitAllowForwardingRequestToParent</a>.
<dl>
<dt><b>STATUS_WDF_BUSY</b></dt>
</dl>The specified I/O queue is not accepting new requests.

 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




A bug check occurs if the driver supplies an invalid object handle.




## -remarks
Before a driver can call <b>WdfRequestForwardToParentDeviceIoQueue</b>, it must call <a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitallowforwardingrequesttoparent.md">WdfPdoInitAllowForwardingRequestToParent</a>.

The driver must use the same <a href="wdf.accessing_data_buffers_in_kmdf_drivers">method to access data buffers</a> (buffered, direct, or neither) for both the parent device and the child device.

If your driver will call <b>WdfRequestForwardToParentDeviceIoQueue</b> to requeue an I/O request, the driver must not use the request object as the parent of other framework objects, such as timer objects or work item objects.

If your driver has called <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetrequestattributes.md">WdfDeviceInitSetRequestAttributes</a> to specify <a href="wdf.framework_object_context_space">context space</a> for the <i>parent</i> device's request objects, the framework does not add this context space to request objects that the driver receives in a child device's queue. The driver can call <a href="..\wdfobject\nf-wdfobject-wdfobjectallocatecontext.md">WdfObjectAllocateContext</a> to add the context space to a request object before the driver calls <b>WdfRequestForwardToParentDeviceIoQueue</b>. On the other hand, if the driver called <b>WdfDeviceInitSetRequestAttributes</b> for the <i>child</i> device's request objects, and if the parent device's request objects use context space that is equal to or smaller than the child device's context space, the driver can use the request object's context space without calling <b>WdfObjectAllocateContext</b>.

Currently, the driver must use the <a href="..\wdfrequest\ne-wdfrequest-_wdf_request_forward_options_flags.md">send and forget option</a> for all requeued I/O requests. Therefore, be aware that by the time that the framework deletes a requeued request object, it might have already removed the child device that originally received the request object. Thus, the driver must not use the <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> or <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a> function of a requeued request object to access child device resources, because the resources might be removed before the <i>EvtCleanupCallback</i> or <i>EvtDestroyCallback</i> function runs.

For more information about <b>WdfRequestForwardToParentDeviceIoQueue</b>, see <a href="https://msdn.microsoft.com/b509959c-b2ab-4f04-9c08-5c5e90726b73">Requeuing I/O Requests</a>.

The following code example first determines the parent device of a device that received an I/O request, and then it requeues the I/O request to the parent device's default I/O queue.


## -see-also
<dl>
<dt>
<a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitallowforwardingrequesttoparent.md">WdfPdoInitAllowForwardingRequestToParent</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestForwardToParentDeviceIoQueue method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

