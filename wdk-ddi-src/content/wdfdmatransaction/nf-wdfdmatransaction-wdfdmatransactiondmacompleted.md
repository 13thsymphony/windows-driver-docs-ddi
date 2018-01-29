---
UID : NF:wdfdmatransaction.WdfDmaTransactionDmaCompleted
title : WdfDmaTransactionDmaCompleted function
author : windows-driver-content
description : The WdfDmaTransactionDmaCompleted method notifies the framework that a device's DMA transfer operation is completed.
old-location : wdf\wdfdmatransactiondmacompleted.htm
old-project : wdf
ms.assetid : 83c1c4cb-b28b-4980-92fb-a1a49d95406e
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdfdmatransaction/WdfDmaTransactionDmaCompleted, WdfDmaTransactionDmaCompleted, wdf.wdfdmatransactiondmacompleted, DFDmaObjectRef_d7fd815f-7c21-4b84-b4f2-0dcc13cf068a.xml, kmdf.wdfdmatransactiondmacompleted, WdfDmaTransactionDmaCompleted method
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfdmatransaction.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2
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


# WdfDmaTransactionDmaCompleted function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaTransactionDmaCompleted</b> method notifies the framework that a device's DMA transfer operation is completed.

## Syntax

````
BOOLEAN WdfDmaTransactionDmaCompleted(
  _In_  WDFDMATRANSACTION DmaTransaction,
  _Out_ NTSTATUS          *Status
);
````

## Parameters

`DmaTransaction`

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>.

`Status`

A pointer to a location that receives the status of the DMA transfer. For more information, see the following Remarks section.


## Return Value

<b>WdfDmaTransactionDmaCompleted</b> returns <b>FALSE</b> and <i>Status</i> receives STATUS_MORE_PROCESSING_REQUIRED if additional transfers are needed to complete the DMA transaction. The method returns <b>TRUE</b> if no additional transfers are required. 

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

Framework-based drivers must call one of the following methods whenever a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">DMA transfer</a> is complete:
<ul>
<li>
<b>WdfDmaTransactionDmaCompleted</b>

</li>
<li>

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompletedwithlength.md">WdfDmaTransactionDmaCompletedWithLength</a>


</li>
<li>

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompletedfinal.md">WdfDmaTransactionDmaCompletedFinal</a>


</li>
</ul>Typically, drivers call these methods from within an <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a> event callback function, after a device interrupt indicates the completion of a DMA transfer operation. A driver for a system-mode DMA device might call these methods from within an <a href="..\wdfdmatransaction\nc-wdfdmatransaction-evt_wdf_dma_transaction_dma_transfer_complete.md">EvtDmaTransactionDmaTransferComplete</a> event callback function.

The framework might divide a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dma-transactions-and-dma-transfers">DMA transaction</a> into several DMA transfer operations. Therefore, the driver must examine the method's return value to determine if additional transfers are required. 

If the method returns <b>FALSE</b>, the <i>Status</i> location receives STATUS_MORE_PROCESSING_REQUIRED and additional DMA operations are required to complete the transaction. Typically, the <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a> event callback function does nothing else at this point. Instead, the framework calls the driver's <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a> event callback function, so the callback function can begin the next transfer. 

If the method returns <b>TRUE</b>, no more transfers will occur for the specified transaction. In this case, a <i>Status</i> value of STATUS_SUCCESS means that the framework did not encounter any errors and the DMA transaction is complete. 

If the driver calls <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionstopsystemtransfer.md">WdfDmaTransactionStopSystemTransfer</a> before calling <b>WdfDmaTransactionDmaCompleted</b>, <b>WdfDmaTransactionDmaCompleted</b> returns <b>TRUE</b> and a <i>Status</i> value of <b>STATUS_CANCELLED</b>.

For transactions that were set for <a href="https://msdn.microsoft.com/windows/hardware/drivers/wdf/">single transfer</a>, <b>WdfDmaTransactionDmaCompleted</b> returns <b>TRUE</b> and a <i>Status</i> value of <b>STATUS_WDF_TOO_MANY_TRANSFERS</b> if the hardware fails to complete the transaction in a single transfer, even though initialization succeeded.
 	This could happen for hardware that reports residual transfers for each DMA operation. For example, the driver programs the device to write 64KB, but the device writes only 60KB.
   In this case, the driver might repeat the DMA operation or reset the device.

Any other value for <i>Status</i> means that the framework detected an error and the DMA transaction might not have been completed.

When <b>WdfDmaTransactionDmaCompleted</b> returns <b>TRUE</b>, the driver typically does the following:
<ul>
<li>
Calls <a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a> or <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionrelease.md">WdfDmaTransactionRelease</a> to delete or reuse the transaction object, respectively.

</li>
<li>
Completes the I/O request, if the DMA transaction is associated with an I/O request. (Drivers complete requests by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a> or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcompletewithinformation.md">WdfRequestCompleteWithInformation</a>.)

</li>
</ul>For more information about completing DMA transfers, see <a href="https://msdn.microsoft.com/86383b9f-9b82-4afa-81ac-2ab09bd8778b">Completing a DMA Transfer</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfdmatransaction.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionrelease.md">WdfDmaTransactionRelease</a>

<a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a>

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompletedwithlength.md">WdfDmaTransactionDmaCompletedWithLength</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a>

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>

<a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a>

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompletedfinal.md">WdfDmaTransactionDmaCompletedFinal</a>

<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcompletewithinformation.md">WdfRequestCompleteWithInformation</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionDmaCompleted method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>