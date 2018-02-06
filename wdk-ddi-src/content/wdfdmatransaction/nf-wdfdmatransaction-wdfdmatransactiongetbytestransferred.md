---
UID: NF:wdfdmatransaction.WdfDmaTransactionGetBytesTransferred
title: WdfDmaTransactionGetBytesTransferred function
author: windows-driver-content
description: The WdfDmaTransactionGetBytesTransferred method returns the total number of bytes that have been transferred for a specified DMA transaction.
old-location: wdf\wdfdmatransactiongetbytestransferred.htm
old-project: wdf
ms.assetid: 32cc50bc-a93b-43ec-98c7-bfaaebbe6c28
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfdmatransaction/WdfDmaTransactionGetBytesTransferred, PFN_WDFDMATRANSACTIONGETBYTESTRANSFERRED, WdfDmaTransactionGetBytesTransferred, DFDmaObjectRef_a8d61436-75d3-4c14-a81b-6ba7adb3c442.xml, WdfDmaTransactionGetBytesTransferred method, kmdf.wdfdmatransactiongetbytestransferred, wdf.wdfdmatransactiongetbytestransferred
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
-	WdfDmaTransactionGetBytesTransferred
product: Windows
targetos: Windows
req.typenames: "*PWDF_DMA_SYSTEM_PROFILE_CONFIG, WDF_DMA_SYSTEM_PROFILE_CONFIG"
req.product: Windows 10 or later.
---


# WdfDmaTransactionGetBytesTransferred function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaTransactionGetBytesTransferred</b> method returns the total number of bytes that have been transferred for a specified DMA transaction.

## Syntax

````
size_t WdfDmaTransactionGetBytesTransferred(
  _In_ WDFDMATRANSACTION DmaTransaction
);
````

## Parameters

`DmaTransaction`

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>.


## Return Value

<b>WdfDmaTransactionGetBytesTransferred</b> returns the total number of bytes that have been transferred for the DMA transaction that the <i>DmaTransaction</i> parameter specified.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

Framework-based drivers typically call <b>WdfDmaTransactionGetBytesTransferred</b> from within an <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a> event callback function, after all DMA transfers are complete, to obtain the final transferred byte count. Drivers typically use the final byte count as input to the <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcompletewithinformation.md">WdfRequestCompleteWithInformation</a> method. For more information about this method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-a-dma-transaction">Completing a DMA Transaction</a>.

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

<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcompletewithinformation.md">WdfRequestCompleteWithInformation</a>

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompleted.md">WdfDmaTransactionDmaCompleted</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionGetBytesTransferred method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>