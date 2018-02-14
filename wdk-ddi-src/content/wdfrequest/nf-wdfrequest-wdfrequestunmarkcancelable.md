---
UID: NF:wdfrequest.WdfRequestUnmarkCancelable
title: WdfRequestUnmarkCancelable function
author: windows-driver-content
description: The WdfRequestUnmarkCancelable method disables cancellation of a specified I/O request.
old-location: wdf\wdfrequestunmarkcancelable.htm
old-project: wdf
ms.assetid: 91740445-e380-4798-a553-e7d502d2ce92
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfRequestUnmarkCancelable method, PFN_WDFREQUESTUNMARKCANCELABLE, wdf.wdfrequestunmarkcancelable, kmdf.wdfrequestunmarkcancelable, wdfrequest/WdfRequestUnmarkCancelable, WdfRequestUnmarkCancelable, DFRequestObjectRef_a20d187a-e056-4cb9-8efb-4021be144597.xml
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
req.ddi-compliance: CompleteCanceledReq, DeferredRequestCompleted, DriverCreate, EvtIoStopCancel, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, MarkCancOnCancReqLocal, ReqIsCancOnCancReq, ReqMarkCancelableSend, ReqNotCanceledLocal
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfRequestUnmarkCancelable
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---


# WdfRequestUnmarkCancelable function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestUnmarkCancelable</b> method disables cancellation of a specified I/O request.

## Syntax

````
NTSTATUS WdfRequestUnmarkCancelable(
  _In_ WDFREQUEST Request
);
````

## Parameters

`Request`

A handle to a framework request object.


## Return Value

<b>WdfRequestUnmarkCancelable</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
An input parameter is invalid or the request is already not cancelable.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The driver does not own the request. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CANCELLED</b></dt>
</dl>
</td>
<td width="60%">
The request has been canceled.

</td>
</tr>
</table>
 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




A bug check occurs if the driver supplies an invalid object handle.

## Remarks

A driver can call <b>WdfRequestUnmarkCancelable</b> to disable cancellation of an I/O request, if the driver previously called <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelable.md">WdfRequestMarkCancelable</a> or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a> to enable cancellation of the request.

If <b>WdfRequestUnmarkCancelable</b> returns a value other than STATUS_CANCELLED, the driver's <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function will not be called for the request.

If the driver previously called <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelable.md">WdfRequestMarkCancelable</a> or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a>, the driver's <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a> with a <i>Status</i> parameter of STATUS_CANCELLED. The <i>EvtRequestCancel</i> callback function does not have to call <b>WdfRequestUnmarkCancelable</b>. If the driver calls <b>WdfRequestComplete</b> outside of its <i>EvtRequestCancel</i> callback function, the driver must first call <b>WdfRequestUnmarkCancelable</b>.

However, the driver must not call <b>WdfRequestUnmarkCancelable</b> after <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a>. In the following Example section, the example stores a local copy of the request handle and then clears it when the <i>EvtRequestCancel</i> callback function calls <b>WdfRequestComplete</b>. The driver does not call <b>WdfRequestUnmarkCancelable</b> if the local copy of the request handle has been cleared. This example uses the framework's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-automatic-synchronization">automatic synchronization</a>  to synchronize the callback functions.

Note that calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548758">WdfObjectReference</a> to add an additional reference to the request object does <i>not</i> enable your driver to call <b>WdfRequestUnmarkCancelable</b> after the driver's <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a>. 

If <b>WdfRequestUnmarkCancelable</b> returns STATUS_CANCELLED, and then <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> completes the request, the driver must not subsequently use the request object.

If <b>WdfRequestUnmarkCancelable</b> returns STATUS_CANCELLED, the driver must not complete the request before the framework calls <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a>.  Otherwise, the framework might call the driver's <i>EvtRequestCancel</i> with an invalid request. For related code examples, please see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559163">IWDFIoRequest::UnmarkCancelable</a>.

For more information about <b>WdfRequestUnmarkCancelable</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/canceling-i-o-requests">Canceling I/O Requests</a>.


#### Examples

The following code example provides simplified versions of the <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_read.md">EvtIoRead</a>, <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> and <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> callback functions that the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/sample-kmdf-drivers">ECHO sample driver</a> contains. This example shows how to call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelable.md">WdfRequestMarkCancelable</a>, <b>WdfRequestUnmarkCancelable</b>, and <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a> in a driver that uses the framework's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-automatic-synchronization">automatic synchronization</a>. (The ECHO sample uses device-level synchronization.)

If your driver does not use the framework's automatic synchronization, see the two examples on <a href="https://msdn.microsoft.com/library/windows/hardware/ff559163">IWDFIoRequest::UnmarkCancelable</a>. While written for a UMDF driver, these examples demonstrate techniques you can use to manage synchronization between the cancel callback and another thread that calls the <i>Unmark</i> routine.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
  EchoEvtIoRead(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request,
    IN size_t  Length
    )
{
    PQUEUE_CONTEXT queueContext = QueueGetContext(Queue);

    // Prepare for read operation here.
    // (See the Echo sample driver for details.) 
 ...
    // Enable cancellation.
    WdfRequestMarkCancelable(
                             Request,
                             EchoEvtRequestCancel
                             );

    // Save the request handle. We'll clear it after
    // we call WdfRequestComplete.
    queueContext-&gt;CurrentRequest = Request;
    return
}


VOID
 EchoEvtRequestCancel(
    IN WDFREQUEST  Request
    )
{
    PQUEUE_CONTEXT queueContext = 
        QueueGetContext(WdfRequestGetIoQueue(Request));

    WdfRequestComplete(
                       Request,
                       STATUS_CANCELLED,
     );
    // Clear the request handle so EchEvtTimerFunc will
    // know that we called WdfRequestComplete.
    queueContext-&gt;CurrentRequest = NULL;

    return;
}


VOID
  EchoEvtTimerFunc(
    IN WDFTIMER  Timer
    )
{
    NTSTATUS  Status;
    WDFREQUEST  Request;
    WDFQUEUE  queue;
    PQUEUE_CONTEXT  queueContext;

    // Retrieve our saved copy of the request handle.
    queue = WdfTimerGetParentObject(Timer);
    queueContext = QueueGetContext(queue);
    Request = queueContext-&gt;CurrentRequest;

    // We cannot call WdfRequestUnmarkCancelable
    // after a request completes, so check here to see
    // if EchoEvtRequestCancel cleared our saved
    // request handle. 
    if( Request != NULL ) {
        Status = WdfRequestUnmarkCancelable(Request);
        if(Status != STATUS_CANCELLED) {
            queueContext-&gt;CurrentRequest = NULL;
            Status = queueContext-&gt;CurrentStatus;
            WdfRequestComplete(
                               Request,
                               Status
                               );
        }
    }

    return;
}</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfrequest.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | CompleteCanceledReq, DeferredRequestCompleted, DriverCreate, EvtIoStopCancel, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, MarkCancOnCancReqLocal, ReqIsCancOnCancReq, ReqMarkCancelableSend, ReqNotCanceledLocal |

## See Also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a>



<a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelable.md">WdfRequestMarkCancelable</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestUnmarkCancelable method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>