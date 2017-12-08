---
UID: NC.wdfio.EVT_WDF_IO_QUEUE_IO_CANCELED_ON_QUEUE
title: EVT_WDF_IO_QUEUE_IO_CANCELED_ON_QUEUE
author: windows-driver-content
description: A driver's EvtIoCanceledOnQueue event callback function informs the driver that it must complete an I/O request that the framework has removed from an I/O queue.
old-location: wdf\evtiocanceledonqueue.htm
old-project: wdf
ms.assetid: 1b938ee8-a5f3-4a1e-9beb-231d88aa5848
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _WDF_INTERRUPT_INFO, WDF_INTERRUPT_INFO, *PWDF_INTERRUPT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: EvtIoCanceledOnQueue
req.alt-loc: Wdfio.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# EVT_WDF_IO_QUEUE_IO_CANCELED_ON_QUEUE callback



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
A driver's <i>EvtIoCanceledOnQueue</i> event callback function informs the driver that it must complete an I/O request that the framework has removed from an I/O queue.


## -prototype

````
EVT_WDF_IO_QUEUE_IO_CANCELED_ON_QUEUE EvtIoCanceledOnQueue;

VOID EvtIoCanceledOnQueue(
  _In_ WDFQUEUE   Queue,
  _In_ WDFREQUEST Request
)
{ ... }
````


## -parameters

### -param Queue [in]

A handle to an I/O queue object.

### -param Request [in]

A handle to a request object.

## -returns
None

## -remarks
A driver registers an <i>EvtIoCanceledOnQueue</i> callback function when it calls the <a href="wdf.wdfioqueuecreate">WdfIoQueueCreate</a> method. For more information about calling <b>WdfIoQueueCreate</b>, see <a href="wdf.creating_i_o_queues">Creating I/O Queues</a>.

If a driver registers an <i>EvtIoCanceledOnQueue</i> callback function for an I/O queue, the framework calls the callback function in the following situations:

A <a href="wdf.request_handlers">request handler</a> receives an I/O request from an I/O queue, the driver calls <a href="wdf.wdfrequestforwardtoioqueue">WdfRequestForwardToIoQueue</a>, <a href="wdf.wdfrequestforwardtoparentdeviceioqueue">WdfRequestForwardToParentDeviceIoQueue</a>, or <a href="wdf.wdfrequestrequeue">WdfRequestRequeue</a> to requeue the request to the I/O queue for which the <i>EvtIoCanceledOnQueue</i> callback function is registered, and the associated I/O operation is subsequently canceled.

The driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_io_in_caller_context.md">EvtIoInCallerContext</a> callback function receives an I/O request, the driver calls <a href="wdf.wdfdeviceenqueuerequest">WdfDeviceEnqueueRequest</a> to pass the request back to the framework, the framework then places the request in the I/O queue for which the <i>EvtIoCanceledOnQueue</i> callback function is registered, and the associated I/O operation is subsequently canceled.

After the framework calls the <i>EvtIoCanceledOnQueue</i> callback function, the driver <a href="wdf.request_ownership">owns</a> the request object and must <a href="https://msdn.microsoft.com/library/windows/hardware/hh406719">complete</a> the request with an appropriate status code, either in <i>EvtIoCanceledOnQueue</i> or later.  When the framework calls <i>EvtIoCanceledOnQueue</i>, the request is still associated with the I/O queue, but the driver cannot requeue the request. The ownership of the request stays with the driver even if the driver does not complete the request in <i>EvtIoCanceledOnQueue</i>. If the driver completes the request after <i>EvtIoCanceledOnQueue</i> returns, it cannot call <a href="wdf.wdfioqueuefindrequest">WdfIoQueueFindRequest</a>  and <a href="wdf.wdfioqueueretrievefoundrequest">WdfIoQueueRetrieveFoundRequest</a> to reacquire ownership of the request because the driver already has ownership of the request.

Typically, in <i>EvtIoCanceledOnQueue</i>, the driver <a href="wdf.completing_i_o_requests">completes the I/O request</a> with a completion status of STATUS_CANCELLED.

In some cases, the driver might have previously requeued an I/O request to a manual queue, perhaps to wait for information.  For example, in one of its <a href="wdf.request_handlers">request handlers</a>, a driver might place an I/O request that is associated with a pending DMA transaction in a manual queue.  In this case, the driver attempts to <a href="wdf.canceling_dma_transactions">cancel the DMA transaction</a> in its <i>EvtIoCanceledOnQueue</i> callback. Depending on the results of the cancel operation, the driver completes the request with an appropriate status, either in <i>EvtIoCanceledOnQueue</i> or later.

The framework does not call the driver's <i>EvtIoCanceledOnQueue</i> callback function for I/O requests that the framework has never delivered to the driver.

The framework calls an <i>EvtIoCanceledOnQueue</i> callback function as soon as it determines that an I/O request has been canceled, regardless of the <a href="wdf.dispatching_methods_for_i_o_requests">dispatching method</a> that the driver has set for the I/O queue. Therefore, the framework can call an <i>EvtIoCanceledOnQueue</i> callback function for:

A request in a queue that uses <a href="wdf.dispatching_methods_for_i_o_requests#sequential_dispatching#sequential_dispatching">sequential dispatching</a>, even if the driver currently owns another request from the queue.

A request in a queue for which the driver has set <a href="wdf.wdf_io_queue_config">NumberOfPresentedRequests</a>, even if the driver currently owns the maximum number of requests.

For more information about the <i>EvtIoCanceledOnQueue</i> callback function, see <a href="wdf.canceling_i_o_requests">Canceling I/O Requests</a>.

The <i>EvtIoCanceledOnQueue</i> callback function can be called at IRQL &lt;= DISPATCH_LEVEL, unless the <b>ExecutionLevel</b> member of the device or driver's <a href="wdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure is set to <b>WdfExecutionLevelPassive</b>.

If the IRQL is PASSIVE_LEVEL, the framework calls the callback function within a <a href="https://msdn.microsoft.com/3781498a-45e9-4f24-8fd2-830eed61298c">critical region</a>.

To define an <i>EvtIoCanceledOnQueue</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

To define an <i>EvtIoCanceledOnQueue</i> callback function, you must first provide a function declaration that SDV and other verification tools require.  The following example is taken from the <a href="http://go.microsoft.com/fwlink/p/?linkid=256155">PCMCIA Smart Card Driver</a> sample.

In the <a href="http://go.microsoft.com/fwlink/p/?linkid=256155">PCMCIA Smart Card Driver</a> sample, the driver uses a manual queue to store pending smart card notification requests. The driver provides an <i>EvtIoCanceledOnQueue</i> callback function in which the driver clears the notification field and completes the request.

The <b>EVT_WDF_IO_QUEUE_IO_CANCELED_ON_QUEUE</b> function type is defined in the Wdfio.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_IO_QUEUE_IO_CANCELED_ON_QUEUE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.

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
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfio.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= DISPATCH_LEVEL (see Remarks section)
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfioqueuecreate">WdfIoQueueCreate</a>
</dt>
<dt>
<a href="wdf.wdfrequestforwardtoioqueue">WdfRequestForwardToIoQueue</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_IO_QUEUE_IO_CANCELED_ON_QUEUE callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
