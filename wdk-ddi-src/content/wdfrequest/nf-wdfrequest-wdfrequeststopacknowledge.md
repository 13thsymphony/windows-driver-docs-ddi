---
UID: NF:wdfrequest.WdfRequestStopAcknowledge
title: WdfRequestStopAcknowledge function
author: windows-driver-content
description: The WdfRequestStopAcknowledge method informs the framework that the driver has stopped processing a specified I/O request.
old-location: wdf\wdfrequeststopacknowledge.htm
old-project: wdf
ms.assetid: 70f90cfd-9828-41a6-a7f9-6b0033e46b74
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfRequestStopAcknowledge
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfRequestStopAcknowledge
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DeferredRequestCompleted, DriverCreate, EvtIoStopCancel, EvtIoStopCompleteOrStopAck, EvtIoStopResume, KmdfIrql, KmdfIrql2, RequestCompleted, RequestCompletedLocal, StopAckWithinEvtIoStop
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestStopAcknowledge function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestStopAcknowledge</b> method informs the framework that the driver has stopped processing a specified I/O request.



## -syntax

````
VOID WdfRequestStopAcknowledge(
  _In_ WDFREQUEST Request,
  _In_ BOOLEAN    Requeue
);
````


## -parameters

### -param Request [in]

A handle to a framework request object.


### -param Requeue [in]

A Boolean value that, if <b>TRUE</b>, causes the framework to requeue the request into the queue so that the framework will deliver it to the driver again. If <b>FALSE</b>, the framework does not requeue the request. For more information, see the following Remarks section.


## -returns
None.

A bug check occurs if the driver supplies an invalid object handle.


## -remarks
If a driver registers an <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_stop.md">EvtIoStop</a> callback function for an I/O queue, the framework calls it when the queue's underlying device is leaving its working (D0) state. The framework calls the <i>EvtIoStop</i> callback function for every I/O request that the driver has not <a href="https://msdn.microsoft.com/library/windows/hardware/dn265386">completed</a>, including requests that the driver <a href="wdf.request_ownership">owns</a> and those that it has <a href="wdf.forwarding_i_o_requests">forwarded</a> to an I/O target. The driver must complete, cancel, or postpone processing of each request by doing one of the following: 

If the driver owns the request, it can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a> to complete or cancel the request.

If the driver has forwarded the request to an I/O target, it can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcancelsentrequest.md">WdfRequestCancelSentRequest</a> to attempt to cancel the request.

If the driver postpones processing the request, it must call <b>WdfRequestStopAcknowledge</b>.

If your driver calls <b>WdfRequestStopAcknowledge</b>, it must call this method from within its <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_stop.md">EvtIoStop</a> callback function.

The framework does not allow the device to leave its working (D0) state until the driver has completed, canceled, or postponed every request that an <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_stop.md">EvtIoStop</a> callback function receives.  Potentially, this inaction can prevent a system from entering its hibernation state or another low system power state.

When a driver's <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_stop.md">EvtIoStop</a> callback function calls <b>WdfRequestStopAcknowledge</b>, it can set the <i>Requeue</i> parameter to <b>TRUE</b> or <b>FALSE</b>: 

Setting <i>Requeue</i> to <b>TRUE</b> causes the framework to place the request back into its I/O queue.

When the underlying device returns to its working (D0) state, the framework will redeliver the request to the driver. 

Setting <i>Requeue</i> to <b>FALSE</b> causes the framework not to requeue the request. If the driver <a href="wdf.request_ownership">owns</a> the request, ownership remains with the driver. If the driver has forwarded the request, the driver is responsible for handling the request when it is completed. The driver must stop doing any I/O processing that requires hardware access. 

When the underlying device returns to its working (D0) state, the framework will call the driver's <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_resume.md">EvtIoResume</a> callback function, so that the driver can continue processing the request.

If the driver had previously called <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelable.md">WdfRequestMarkCancelable</a> or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a>, it must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestunmarkcancelable.md">WdfRequestUnmarkCancelable</a> before calling <b>WdfRequestStopAcknowledge</b> with <i>Requeue</i> set to <b>TRUE</b>.

Before calling <b>WdfRequestStopAcknowledge</b>, the driver's <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_stop.md">EvtIoStop</a> callback function must stop all processing of the I/O request that requires accessing the underlying device, because the device is about to enter a low-power state.

For more information about the <b>WdfRequestStopAcknowledge</b> method, see <a href="https://msdn.microsoft.com/271d55ef-d82e-4ffd-bf41-a602c42c3f0e">Using Power-Managed I/O Queues</a>.

If a driver calls <b>WdfRequestStopAcknowledge</b> with <i>Requeue</i> set to <b>TRUE</b>, it must previously call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestunmarkcancelable.md">WdfRequestUnmarkCancelable</a>.

The following code example is an <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_stop.md">EvtIoStop</a> callback function that checks to see if a received request is cancelable and, if it is, calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestunmarkcancelable.md">WdfRequestUnmarkCancelable</a>. If <b>WdfRequestUnmarkCancelable</b> returns STATUS_CANCELLED, the example just returns because the driver's <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function will handle the request. Otherwise, the example calls <b>WdfRequestStopAcknowledge</b> and specifies <b>TRUE</b> so that the framework requeues the request when the underlying device returns to its working (D0) state.

Typically, if a driver calls <b>WdfRequestStopAcknowledge</b> with <i>Requeue</i> set to <b>FALSE</b>, it leaves the request cancelable.

The following code example is an <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_stop.md">EvtIoStop</a> callback function that calls <b>WdfRequestStopAcknowledge</b> and specifies <b>FALSE</b> so that the framework eventually calls the driver's <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_resume.md">EvtIoResume</a> callback function, where the driver resumes processing of the request.

You might use code like this if it is acceptable to halt processing of a specific request and continue it later, rather than having the request redelivered and restarting processing from the beginning.


## -see-also
<dl>
<dt>
<a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_stop.md">EvtIoStop</a>
</dt>
<dt>
<a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestStopAcknowledge method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

