---
UID: NF:wdfdmatransaction.WdfDmaTransactionDmaCompletedFinal
title: WdfDmaTransactionDmaCompletedFinal function
author: windows-driver-content
description: The WdfDmaTransactionDmaCompletedFinal method notifies the framework that a device's DMA transfer operation has completed with an underrun condition and supplies the length of the completed transfer.
old-location: wdf\wdfdmatransactiondmacompletedfinal.htm
old-project: wdf
ms.assetid: de16eaf4-11f0-428b-8833-1d1e6ef78853
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfdmatransaction/WdfDmaTransactionDmaCompletedFinal, DFDmaObjectRef_ceac647e-264e-416b-947f-61cc95e6d4ab.xml, PFN_WDFDMATRANSACTIONDMACOMPLETEDFINAL, WdfDmaTransactionDmaCompletedFinal, kmdf.wdfdmatransactiondmacompletedfinal, WdfDmaTransactionDmaCompletedFinal method, wdf.wdfdmatransactiondmacompletedfinal
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
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
apiname:
-	WdfDmaTransactionDmaCompletedFinal
product: Windows
targetos: Windows
req.typenames: "*PWDF_DMA_SYSTEM_PROFILE_CONFIG, WDF_DMA_SYSTEM_PROFILE_CONFIG"
req.product: Windows 10 or later.
---


# WdfDmaTransactionDmaCompletedFinal function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaTransactionDmaCompletedFinal</b> method notifies the framework that a device's DMA transfer operation has completed with an underrun condition and supplies the length of the completed transfer.

## Syntax

````
BOOLEAN WdfDmaTransactionDmaCompletedFinal(
  _In_  WDFDMATRANSACTION DmaTransaction,
  _In_  size_t            FinalTransferredLength,
  _Out_ NTSTATUS          *Status
);
````

## Parameters

`DmaTransaction`

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>.

`FinalTransferredLength`

The number of bytes that the device transferred.

`Status`

A pointer to a location that receives the status of the DMA transfer. For more information, see the Remarks section for <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompleted.md">WdfDmaTransactionDmaCompleted</a>.


## Return Value

<b>WdfDmaTransactionDmaCompletedFinal</b> returns <b>FALSE</b> if the driver supplies an invalid input parameter. Otherwise, <b>WdfDmaTransactionDmaCompletedFinal</b> always returns <b>TRUE</b>, which indicates that the framework will not attempt to transfer any more bytes for the DMA transaction that the <i>DmaTransaction</i> parameter specified. 

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

A driver typically calls <b>WdfDmaTransactionDmaCompletedFinal</b> from within its <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a> callback. A driver for a system-mode DMA device might call <b>WdfDmaTransactionDmaCompletedFinal</b> from within an <a href="..\wdfdmatransaction\nc-wdfdmatransaction-evt_wdf_dma_transaction_dma_transfer_complete.md">EvtDmaTransactionDmaTransferComplete</a> event callback function.

In the  <a href="http://go.microsoft.com/fwlink/p/?linkid=256157">PLX9x5x</a> sample, the driver calls  <b>WdfDmaTransactionDmaCompletedFinal</b> from its <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a> callback function.

The <b>WdfDmaTransactionDmaCompletedFinal</b> method behaves the same as <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompleted.md">WdfDmaTransactionDmaCompleted</a>, except that drivers typically call <b>WdfDmaTransactionDmaCompletedFinal</b> if the hardware reports an underrun condition. An underrun condition means that the hardware could not transfer all of the bytes that were specified for the last DMA transfer. A call to <b>WdfDmaTransactionDmaCompletedFinal</b> stops the framework from starting any more DMA transfers for the specified DMA transaction.

When your driver calls <b>WdfDmaTransactionDmaCompletedFinal</b>, the driver supplies the number of bytes that were transferred. The return value is always <b>TRUE</b>, because the framework will not attempt to transfer any more bytes for the specified transaction. 

For more information about completing DMA transfers, see <a href="https://msdn.microsoft.com/86383b9f-9b82-4afa-81ac-2ab09bd8778b">Completing a DMA Transfer</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfdmatransaction.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompletedwithlength.md">WdfDmaTransactionDmaCompletedWithLength</a>

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompleted.md">WdfDmaTransactionDmaCompleted</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionDmaCompletedFinal method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>