---
UID : NF:wdfdmatransaction.WdfDmaTransactionDmaCompletedWithLength
title : WdfDmaTransactionDmaCompletedWithLength function
author : windows-driver-content
description : The WdfDmaTransactionDmaCompletedWithLength method notifies the framework that a device's DMA transfer operation is complete and supplies the length of the completed transfer.
old-location : wdf\wdfdmatransactiondmacompletedwithlength.htm
old-project : wdf
ms.assetid : 7f436ac1-1e36-449c-a23f-b5729e5a20c2
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : kmdf.wdfdmatransactiondmacompletedwithlength, DFDmaObjectRef_b04fb6c6-98ce-4d3b-8bc9-10a29f6bde46.xml, wdfdmatransaction/WdfDmaTransactionDmaCompletedWithLength, WdfDmaTransactionDmaCompletedWithLength method, PFN_WDFDMATRANSACTIONDMACOMPLETEDWITHLENGTH, wdf.wdfdmatransactiondmacompletedwithlength, WdfDmaTransactionDmaCompletedWithLength
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


# WdfDmaTransactionDmaCompletedWithLength function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaTransactionDmaCompletedWithLength</b> method notifies the framework that a device's DMA transfer operation is complete and supplies the length of the completed transfer.

## Syntax

````
BOOLEAN WdfDmaTransactionDmaCompletedWithLength(
  _In_  WDFDMATRANSACTION DmaTransaction,
  _In_  size_t            TransferredLength,
  _Out_ NTSTATUS          *Status
);
````

## Parameters

`DmaTransaction`

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>.

`TransferredLength`

The number of bytes that the device transferred in the current DMA transfer.

`Status`

A pointer to a location that receives the status of the DMA transfer. For more information, see the Remarks section for <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompleted.md">WdfDmaTransactionDmaCompleted</a>.


## Return Value

<b>WdfDmaTransactionDmaCompletedWithLength</b> returns <b>FALSE</b> and <i>Status</i> receives STATUS_MORE_PROCESSING_REQUIRED if additional transfers are needed to complete the DMA transaction. The method returns <b>TRUE</b> if no additional transfers are required. 

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

When your driver calls the <b>WdfDmaTransactionDmaCompletedWithLength</b> method, the framework ends the current transfer and, if necessary, starts a new one.

The <b>WdfDmaTransactionDmaCompletedWithLength</b> method behaves the same as <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompleted.md">WdfDmaTransactionDmaCompleted</a>, except that drivers call <b>WdfDmaTransactionDmaCompletedWithLength</b> for devices that report the number of bytes that were transferred. The framework uses the reported byte count to determine the beginning of the next DMA transfer for the specified DMA transaction, if multiple transfers are needed to complete the transaction.

For more information about completing DMA transfers, see <a href="https://msdn.microsoft.com/86383b9f-9b82-4afa-81ac-2ab09bd8778b">Completing a DMA Transfer</a>.

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

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompleted.md">WdfDmaTransactionDmaCompleted</a>

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiongetcurrentdmatransferlength.md">WdfDmaTransactionGetCurrentDmaTransferLength</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionDmaCompletedWithLength method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>