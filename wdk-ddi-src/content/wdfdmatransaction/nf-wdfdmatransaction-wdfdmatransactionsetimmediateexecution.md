---
UID: NF:wdfdmatransaction.WdfDmaTransactionSetImmediateExecution
title: WdfDmaTransactionSetImmediateExecution function
author: windows-driver-content
description: The WdfDmaTransactionSetImmediateExecution method marks the specified DMA transaction so that calls to WdfDmaTransactionExecute and WdfDmaTransactionAllocateResources initiate the transaction immediately or fail.
old-location: wdf\wdfdmatransactionsetimmediateexecution.htm
old-project: wdf
ms.assetid: BC260058-1E33-43BA-B75E-79540E36A08D
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfDmaTransactionSetImmediateExecution, WdfDmaTransactionSetImmediateExecution method, kmdf.wdfdmatransactionsetimmediateexecution, wdf.wdfdmatransactionsetimmediateexecution, wdfdmatransaction/WdfDmaTransactionSetImmediateExecution
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
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDmaTransactionSetImmediateExecution
product: Windows
targetos: Windows
req.typenames: WDF_DMA_SYSTEM_PROFILE_CONFIG, *PWDF_DMA_SYSTEM_PROFILE_CONFIG
req.product: Windows 10 or later.
---


# WdfDmaTransactionSetImmediateExecution function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaTransactionSetImmediateExecution</b> method
   marks the specified DMA transaction so  that calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547062">WdfDmaTransactionExecute</a>  and <a href="https://msdn.microsoft.com/library/windows/hardware/hh451123">WdfDmaTransactionAllocateResources</a> initiate the transaction immediately or fail.

## Syntax

```
void WdfDmaTransactionSetImmediateExecution(
  WDFDMATRANSACTION DmaTransaction,
  BOOLEAN           UseImmediateExecution
);
```

## Parameters

`DmaTransaction`

A handle to a DMA transaction object to mark for immediate execution.

`UseImmediateExecution`

A Boolean value which, if TRUE, indicates that the transaction should execute immediately (or fail if resources are not available), and, if FALSE, indicates that the transaction should be queued for execution once DMA resources are available.


## Return Value

This method does not return a value.

## Remarks

Before calling <b>WdfDmaTransactionSetImmediateExecution</b>, the driver must initialize the transaction.

If the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547062">WdfDmaTransactionExecute</a>  or <a href="https://msdn.microsoft.com/library/windows/hardware/hh451123">WdfDmaTransactionAllocateResources</a> after calling <b>WdfDmaTransactionSetImmediateExecution</b> with <i>UseImmediateExecution</i> set to TRUE, and the resources needed for the request are unavailable, that method returns STATUS_INSUFFICIENT_RESOURCES. If the required resources are available, the framework claims them and initiates the call synchronously.

After the driver marks a transaction for immediate execution, the transaction remains marked as such until the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547114">WdfDmaTransactionRelease</a> or clears the flag by calling <b>WdfDmaTransactionSetImmediateExecution</b> with <i>UseImmediateExecution</i> set to FALSE.

<b>WdfDmaTransactionSetImmediateExecution</b> requires DMA version 3.
 To select DMA version 3, set the <b>WdmDmaVersionOverride</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff551290">WDF_DMA_ENABLER_CONFIG</a> to 3.

If your driver calls this method on an operating system earlier than Windows 8, <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-kmdf-verifier">the framework's verifier</a> reports an error.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8  |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.11 |
| **Header** | wdfdmatransaction.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451123">WdfDmaTransactionAllocateResources</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547062">WdfDmaTransactionExecute</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547114">WdfDmaTransactionRelease</a>