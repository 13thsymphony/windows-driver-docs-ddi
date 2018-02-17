---
UID: NC:wdfdmatransaction.EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE
title: EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE
author: windows-driver-content
description: A driver's EvtDmaTransactionDmaTransferComplete event callback function is called when the system-mode controller has completed the current DMA transfer.
old-location: wdf\evtdmatransactiondmatransfercomplete.htm
old-project: wdf
ms.assetid: C638A505-AAE1-48FC-B06B-F2F161ADC948
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdmatransactiondmatransfercomplete, EvtDmaTransactionDmaTransferComplete callback function, EvtDmaTransactionDmaTransferComplete, EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE, EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE, wdfdmatransaction/EvtDmaTransactionDmaTransferComplete, kmdf.evtdmatransactiondmatransfercomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	WdfDmaTransaction.h
apiname:
-	EvtDmaTransactionDmaTransferComplete
product: Windows
targetos: Windows
req.typenames: "*PWDF_DMA_SYSTEM_PROFILE_CONFIG, WDF_DMA_SYSTEM_PROFILE_CONFIG"
req.product: Windows 10 or later.
---


# EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE function
<p class="CCE_Message">[Applies to KMDF only]


   A driver's <i>EvtDmaTransactionDmaTransferComplete</i> event callback function is called when  the system-mode controller has completed the current DMA transfer.

## Syntax

```
EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE EvtWdfDmaTransactionDmaTransferComplete;

void EvtWdfDmaTransactionDmaTransferComplete(
  WDFDMATRANSACTION Transaction,
  WDFDEVICE Device,
  WDFCONTEXT Context,
  WDF_DMA_DIRECTION Direction,
  DMA_COMPLETION_STATUS Status
)
{...}
```

## Parameters

`Transaction`

A handle to a DMA transaction object representing the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">DMA transfer</a> that has just completed.

`Device`

A handle to the framework device object that the driver specified when it called <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>.

`Context`

The context pointer that the driver specified in a previous call to <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionsettransfercompletecallback.md">WdfDmaTransactionSetTransferCompleteCallback</a>.

`Direction`

A <a href="..\wdfdmaenabler\ne-wdfdmaenabler-_wdf_dma_direction.md">WDF_DMA_DIRECTION</a>-typed value that specifies the direction of the completing DMA transfer operation.

`Status`

A <a href="..\wdm\ne-wdm-dma_completion_status.md">DMA_COMPLETION_STATUS</a>-typed value that specifies the status of the transfer.


## Return Value

This callback function does not return a value.

## Remarks

The hardware for a bus-master DMA device typically issues an interrupt when a DMA transfer is complete. The driver then completes the DMA transfer in its <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a>  callback function.

However, the hardware for a system-mode DMA device does not always signal DMA transfer completion by issuing an interrupt. To receive notification of DMA transfer completion, a driver for a system-mode DMA device can instead register an <i>EvtDmaTransactionDmaTransferComplete</i> event callback function by calling <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionsettransfercompletecallback.md">WdfDmaTransactionSetTransferCompleteCallback</a>.

The framework calls <i>EvtDmaTransactionDmaTransferComplete</i> after the system DMA controller has completed the transfer, once for each transfer in a transaction.

From within its <i>EvtDmaTransactionDmaTransferComplete</i> callback, the driver can call the following methods to notify the framework that the transfer has completed:

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompleted.md">WdfDmaTransactionDmaCompleted</a>
<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompletedfinal.md">WdfDmaTransactionDmaCompletedFinal</a>
<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompletedwithlength.md">WdfDmaTransactionDmaCompletedWithLength</a>
The driver might not call one of the previous methods from <i>EvtDmaTransactionDmaTransferComplete</i>, opting instead to <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-timers">create a timer object</a> or schedule a DPC to complete the transfer later, as needed. After <b>WdfDmaTransactionDmaCompleted</b><i>Xxx</i> returns TRUE, indicating that no more transfers are needed to complete the DMA transaction, the driver can optionally call  <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionexecute.md">WdfDmaTransactionExecute</a> to initiate a subsequent transaction.

If the driver calls <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionstopsystemtransfer.md">WdfDmaTransactionStopSystemTransfer</a>, the framework calls <i>EvtDmaTransactionDmaTransferComplete</i> with a <i>Status</i> value of <b>DmaCancelled</b>.  In this case, the driver should call <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompletedfinal.md">WdfDmaTransactionDmaCompletedFinal</a> from within <i>EvtDmaTransactionDmaTransferComplete</i>, and then can continue with request processing.

The driver must not manipulate the data buffers associated with the transaction until after <b>WdfDmaTransactionDmaCompleted</b><i>Xxx</i> has returned TRUE.

The driver can call <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionrelease.md">WdfDmaTransactionRelease</a> from within <i>EvtDmaTransactionDmaTransferComplete</i> if it needs to terminate the DMA transaction.

For more information about system-mode DMA, see <a href="https://msdn.microsoft.com/CCC77C15-69CA-44CB-8DEB-29F3EAEA44F6">Supporting System-Mode DMA</a>.


#### Examples

To define an <i>EvtDmaTransactionDmaTransferComplete</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDmaTransactionDmaTransferComplete</i> callback function that is named <i>MyDmaTransactionDmaTransferComplete</i>, use the <b>EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE  MyDmaTransactionDmaTransferComplete;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
_Use_decl_annotations_
VOID
MyDmaTransactionDmaTransferComplete(
    WDFDMATRANSACTION Transaction,
    WDFDEVICE /* Device */,
    WDFCONTEXT Context,
    WDF_DMA_DIRECTION /* Direction */,
    DMA_COMPLETION_STATUS DmaStatus
    )
{
    PREQUEST_CONTEXT requestContext = (PREQUEST_CONTEXT) Context;
    NTSTATUS requestStatus;
    bool overrideStatus = true;
    size_t bytesTransferred;

    if (DmaStatus == DmaComplete) {
        //
        // Normal transfer completion.  Indicate this to the framework and see 
        // if there's more work to do.
        //
        if (WdfDmaTransactionDmaCompleted(Transaction, &amp;requestStatus) == FALSE) {
            //
            // There are more DMA transfers to come.  The transaction 
            // may already have been completed on another processor.  
            // Return without touching it again.
            //
            goto exit;
        }

        requestStatus = STATUS_SUCCESS;
    }
    else {

        //
        // Complete the entire transaction.  But throw out the status and 
        // use one derived from the DmaStatus.
        //
        WdfDmaTransactionDmaCompletedFinal(Transaction, 0, &amp;requestStatus);        
        
        //
        // Error or cancellation.  Indicate that this was the final transfer to 
        // the framework.
        //
        if (DmaStatus == DmaError) {
            requestStatus = STATUS_DEVICE_DATA_ERROR;
        }
        else {

            //
            // Cancel status should only be triggered by timeout or cancel.  Rely on 
            // someone having already set the status, which means we should lose
            // the race for BeginCompletion below.
            //
            requestStatus = STATUS_PENDING;
            overrideStatus = false;
        }
    }

    //
    // Begin completion.  There's nothing special to do here if cancel or
    // timeout got there first.
    //
    BeginCompletion(requestContext, requestStatus, overrideStatus);

    //
    // Record the number of bytes we transferred.
    //
    bytesTransferred = WdfDmaTransactionGetBytesTransferred(
                        requestContext-&gt;DmaTransaction
                        );

    WdfRequestSetInformation(requestContext-&gt;Request, bytesTransferred);

    //
    // Success, error or cancel, this was the last transfer in the 
    // transaction.  Attempt to complete the request.
    //
    AttemptRequestCompletion(requestContext, true);

exit: 
    return;
}

bool
BeginCompletion(
    __in PREQUEST_CONTEXT  RequestContext,
    __in NTSTATUS          CompletionStatus,
    __in bool              ForceStatusUpdate
    )
{
    bool completionStarted;

    //
    // Grab the object lock and mark the beginning of 
    // completion.
    //
    WdfSpinLockAcquire(RequestContext-&gt;Lock);

    completionStarted = RequestContext-&gt;CompletionStarted;
    RequestContext-&gt;CompletionStarted = true;

    if ((completionStarted == false) || 
        (ForceStatusUpdate == true)) {
        RequestContext-&gt;CompletionStatus = CompletionStatus;
    }

    WdfSpinLockRelease(RequestContext-&gt;Lock);

    return !completionStarted;
}

VOID
AttemptRequestCompletion(
    __in PREQUEST_CONTEXT RequestContext,
    __in bool TransferComplete
    )
{
    LONG refCount;

    NT_ASSERTMSG("No thread has begun completion", 
                 RequestContext-&gt;CompletionStarted == true);

    if (TransferComplete) {
        //
        // Unmark the request cancelable.  If that succeeds then drop the cancel reference
        //
        if (WdfRequestUnmarkCancelable(RequestContext-&gt;Request) == STATUS_SUCCESS) {
            refCount = InterlockedDecrement(&amp;(RequestContext-&gt;CompletionRefCount));
            NT_ASSERTMSGW(L"Reference count should not have gone to zero yet",
                          refCount != 0);
        }
                
        //
        // Stop the timer if it's been started.
        //
        if (RequestContext-&gt;TimerStarted == true) {
            if (WdfTimerStop(RequestContext-&gt;Timer, FALSE) == TRUE) {
                //
                // The timer was queued but will never run.  Drop its 
                // reference count.
                //
                refCount = InterlockedDecrement(&amp;RequestContext-&gt;CompletionRefCount);
                NT_ASSERTMSG("Completion reference count should not reach zero until "
                             L"this routine calls AttemptRequestCompletion",
                             refCount &gt; 0);
            }
        }
    }

    //
    // Drop this caller's reference.  If that was the last one then 
    // complete the request.
    //
    refCount = InterlockedDecrement(&amp;(RequestContext-&gt;CompletionRefCount));

    if (refCount == 0) {
        NT_ASSERTMSGW(L"Execution reference was released, but execution "
                      L"path did not set a completion status for the "
                      L"request",
                      RequestContext-&gt;CompletionStatus != STATUS_PENDING);
        
        
        //
        // Timers are disposed of at passive level.  If we leave it attached to 
        // the request then we can hit a verifier issue, since the request 
        // needs to be immediately disposable at dispatch-level.
        //
        // Delete the timer now so that we can complete the request safely.
        // At this point the timer has either expired or been succesfully 
        // cancelled so there's no race with the timer routine.
        //
        if (RequestContext-&gt;Timer != NULL) {
            WdfObjectDelete(RequestContext-&gt;Timer);
            RequestContext-&gt;Timer = NULL;
        }

        WdfRequestComplete(RequestContext-&gt;Request, 
                           RequestContext-&gt;CompletionStatus);
    }
}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE</b> function type is defined in the WdfDmaTransaction.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8  |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.11 |
| **Header** | wdfdmatransaction.h (include Wdf.h) |
| **IRQL** | DISPATCH_LEVEL |

## See Also

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionsettransfercompletecallback.md">WdfDmaTransactionSetTransferCompleteCallback</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>