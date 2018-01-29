---
UID : NF:wdfdmatransaction.WdfDmaTransactionSetTransferCompleteCallback
title : WdfDmaTransactionSetTransferCompleteCallback function
author : windows-driver-content
description : The WdfDmaTransactionSetTransferCompleteCallback method registers a transfer completion event callback function for a system-mode DMA transaction.
old-location : wdf\wdfdmatransactionsettransfercompletecallback.htm
old-project : wdf
ms.assetid : B97FF6B1-BFCB-4293-B2F0-EE08E12CFCFF
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfDmaTransactionSetTransferCompleteCallback method, PFN_WDFDMATRANSACTIONSETTRANSFERCOMPLETECALLBACK, wdf.wdfdmatransactionsettransfercompletecallback, kmdf.wdfdmatransactionsettransfercompletecallback, wdfdmatransaction/WdfDmaTransactionSetTransferCompleteCallback, WdfDmaTransactionSetTransferCompleteCallback
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfdmatransaction.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : 
req.kmdf-ver : 1.11
req.umdf-ver : 
req.ddi-compliance : DriverCreate
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (see Framework Library Versioning.)
req.dll : 
req.irql : "<=DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_DMA_SYSTEM_PROFILE_CONFIG, *PWDF_DMA_SYSTEM_PROFILE_CONFIG
req.product : Windows 10 or later.
---


# WdfDmaTransactionSetTransferCompleteCallback function
<p class="CCE_Message">[Applies to KMDF only]


   The <b>WdfDmaTransactionSetTransferCompleteCallback</b> method registers a transfer completion event callback function for a system-mode DMA transaction.

## Syntax

````
void WdfDmaTransactionSetTransferCompleteCallback(
  _In_     WDFDMATRANSACTION                             DmaTransaction,
  _In_opt_ PFN_WDF_DMA_TRANSACTION_DMA_TRANSFER_COMPLETE DmaCompletionRoutine,
  _In_opt_ PVOID                                         DmaCompletionContext
);
````

## Parameters

`DmaTransaction`

A handle to an initialized DMA transaction object for which to set or clear the transfer completion callback.

`DmaCompletionRoutine`

A pointer to the driver's <a href="..\wdfdmatransaction\nc-wdfdmatransaction-evt_wdf_dma_transaction_dma_transfer_complete.md">EvtDmaTransactionDmaTransferComplete</a> event callback function, or NULL to clear a previously set callback function.

`DmaCompletionContext`

A pointer to a buffer containing the driver-specified context to be provided to the driver's <a href="..\wdfdmatransaction\nc-wdfdmatransaction-evt_wdf_dma_transaction_dma_transfer_complete.md">EvtDmaTransactionDmaTransferComplete</a> event callback function, or NULL.


## Return Value

This method does not return a value.

## Remarks

The driver calls this method to set a completion routine that the framework calls after the system DMA controller completes a transfer.  The framework calls the driver's <a href="..\wdfdmatransaction\nc-wdfdmatransaction-evt_wdf_dma_transaction_dma_transfer_complete.md">EvtDmaTransactionDmaTransferComplete</a> callback once for each transfer in the transaction.

Typically from within an <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">I/O queue event callback function</a>, a driver performs the following steps, in this order:
<ol>
<li>Calls <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitializeusingrequest.md">WdfDmaTransactionInitializeUsingRequest</a>, <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitialize.md">WdfDmaTransactionInitialize</a>, or  <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitializeusingoffset.md">WdfDmaTransactionInitializeUsingOffset</a>  to initialize the transaction object.</li>
<li>Calls <b>WdfDmaTransactionSetTransferCompleteCallback</b> on the transaction object.</li>
<li>Calls <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionexecute.md">WdfDmaTransactionExecute</a>.</li>
</ol>If the driver has specified an <a href="..\wdfdmatransaction\nc-wdfdmatransaction-evt_wdf_dma_transaction_dma_transfer_complete.md">EvtDmaTransactionDmaTransferComplete</a> event callback function by calling <b>WdfDmaTransactionSetTransferCompleteCallback</b> and the driver subsequently calls <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionrelease.md">WdfDmaTransactionRelease</a>, the callback is cleared.

<b>WdfDmaTransactionSetTransferCompleteCallback</b> can only be used with a DMA enabler that specifies a system-mode DMA profile.

If your driver calls this method on an operating system earlier than Windows 8, <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-kmdf-verifier">the framework's verifier</a> reports an error.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.11 |
| **Minimum UMDF version** |  |
| **Header** | wdfdmatransaction.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** | DriverCreate |

## See Also

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionrelease.md">WdfDmaTransactionRelease</a>

<a href="..\wdfdmatransaction\nc-wdfdmatransaction-evt_wdf_dma_transaction_dma_transfer_complete.md">EvtDmaTransactionDmaTransferComplete</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionSetTransferCompleteCallback method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>