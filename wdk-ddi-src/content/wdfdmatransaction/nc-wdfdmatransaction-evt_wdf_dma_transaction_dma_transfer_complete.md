---
UID: NC:wdfdmatransaction.EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE
title: EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE function
author: windows-driver-content
description: A driver's EvtDmaTransactionDmaTransferComplete event callback function is called when the system-mode controller has completed the current DMA transfer.
old-location: wdf\evtdmatransactiondmatransfercomplete.htm
old-project: wdf
ms.assetid: C638A505-AAE1-48FC-B06B-F2F161ADC948
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.alt-api: EvtDmaTransactionDmaTransferComplete
req.alt-loc: WdfDmaTransaction.h
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
req.typenames: WDF_DMA_SYSTEM_PROFILE_CONFIG, *PWDF_DMA_SYSTEM_PROFILE_CONFIG
req.product: Windows 10 or later.
---

# EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE function



## -description
<p class="CCE_Message">[Applies to KMDF only]


   A driver's <i>EvtDmaTransactionDmaTransferComplete</i> event callback function is called when  the system-mode controller has completed the current DMA transfer.



## -syntax

````
EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE EvtDmaTransactionDmaTransferComplete;

void EvtDmaTransactionDmaTransferComplete(
  _In_ WDFDMATRANSACTION     Transaction,
  _In_ WDFDEVICE             Device,
  _In_ WDFCONTEXT            Context,
  _In_ WDF_DMA_DIRECTION     Direction,
  _In_ DMA_COMPLETION_STATUS Status
)
{ ... }
````


## -parameters

### -param Transaction [in]

A handle to a DMA transaction object representing the <a href="wdf.dma_transactions_and_dma_transfers">DMA transfer</a> that has just completed.


### -param Device [in]

A handle to the framework device object that the driver specified when it called <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>.


### -param Context [in]

The context pointer that the driver specified in a previous call to <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionsettransfercompletecallback.md">WdfDmaTransactionSetTransferCompleteCallback</a>.


### -param Direction [in]

A <a href="..\wdfdmaenabler\ne-wdfdmaenabler-_wdf_dma_direction.md">WDF_DMA_DIRECTION</a>-typed value that specifies the direction of the completing DMA transfer operation.


### -param Status [in]

A <a href="..\wdm\ne-wdm-dma_completion_status.md">DMA_COMPLETION_STATUS</a>-typed value that specifies the status of the transfer.


## -returns
This callback function does not return a value.


## -remarks
The hardware for a bus-master DMA device typically issues an interrupt when a DMA transfer is complete. The driver then completes the DMA transfer in its <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a>  callback function.

However, the hardware for a system-mode DMA device does not always signal DMA transfer completion by issuing an interrupt. To receive notification of DMA transfer completion, a driver for a system-mode DMA device can instead register an <i>EvtDmaTransactionDmaTransferComplete</i> event callback function by calling <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionsettransfercompletecallback.md">WdfDmaTransactionSetTransferCompleteCallback</a>.

The framework calls <i>EvtDmaTransactionDmaTransferComplete</i> after the system DMA controller has completed the transfer, once for each transfer in a transaction.

From within its <i>EvtDmaTransactionDmaTransferComplete</i> callback, the driver can call the following methods to notify the framework that the transfer has completed:

The driver might not call one of the previous methods from <i>EvtDmaTransactionDmaTransferComplete</i>, opting instead to <a href="wdf.using_timers">create a timer object</a> or schedule a DPC to complete the transfer later, as needed. After <b>WdfDmaTransactionDmaCompleted</b><i>Xxx</i> returns TRUE, indicating that no more transfers are needed to complete the DMA transaction, the driver can optionally call  <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionexecute.md">WdfDmaTransactionExecute</a> to initiate a subsequent transaction.

If the driver calls <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionstopsystemtransfer.md">WdfDmaTransactionStopSystemTransfer</a>, the framework calls <i>EvtDmaTransactionDmaTransferComplete</i> with a <i>Status</i> value of <b>DmaCancelled</b>.  In this case, the driver should call <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompletedfinal.md">WdfDmaTransactionDmaCompletedFinal</a> from within <i>EvtDmaTransactionDmaTransferComplete</i>, and then can continue with request processing.

The driver must not manipulate the data buffers associated with the transaction until after <b>WdfDmaTransactionDmaCompleted</b><i>Xxx</i> has returned TRUE.

The driver can call <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionrelease.md">WdfDmaTransactionRelease</a> from within <i>EvtDmaTransactionDmaTransferComplete</i> if it needs to terminate the DMA transaction.

For more information about system-mode DMA, see <a href="https://msdn.microsoft.com/CCC77C15-69CA-44CB-8DEB-29F3EAEA44F6">Supporting System-Mode DMA</a>.

To define an <i>EvtDmaTransactionDmaTransferComplete</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDmaTransactionDmaTransferComplete</i> callback function that is named <i>MyDmaTransactionDmaTransferComplete</i>, use the <b>EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE</b> type as shown in this code example:

Then, implement your callback function as follows.

The <b>EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE</b> function type is defined in the WdfDmaTransaction.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.


## -see-also
<dl>
<dt>
<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionsettransfercompletecallback.md">WdfDmaTransactionSetTransferCompleteCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

