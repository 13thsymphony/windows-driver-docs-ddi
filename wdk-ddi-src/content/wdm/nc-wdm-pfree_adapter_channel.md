---
UID: NC:wdm.PFREE_ADAPTER_CHANNEL
title: PFREE_ADAPTER_CHANNEL
author: windows-driver-content
description: The FreeAdapterChannel routine releases the system DMA controller when a driver has completed all DMA operations necessary to satisfy the current IRP.
old-location: kernel\freeadapterchannel.htm
old-project: kernel
ms.assetid: 916531dd-4768-436a-910c-07d49924ac48
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: FreeAdapterChannel, FreeAdapterChannel callback function [Kernel-Mode Driver Architecture], PFREE_ADAPTER_CHANNEL, kdma_f48025a6-96a2-4bdd-8b48-6c939bdf738b.xml, kernel.freeadapterchannel, wdm/FreeAdapterChannel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlDispatch, IrqlDispatch(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wdm.h
api_name:
-	FreeAdapterChannel
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---


# PFREE_ADAPTER_CHANNEL callback function
The <b>FreeAdapterChannel</b> routine releases the system DMA controller when a driver has completed all DMA operations necessary to satisfy the current IRP.

## Syntax

```
PFREE_ADAPTER_CHANNEL PfreeAdapterChannel;

void PfreeAdapterChannel(
  PDMA_ADAPTER DmaAdapter
)
{...}
```

## Parameters

`DmaAdapter`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a>  structure returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.


## Return Value

None

## Remarks

<b>FreeAdapterChannel</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>.

After a driver has transferred all the data and called <a href="https://msdn.microsoft.com/library/windows/hardware/ff545917">FlushAdapterBuffers</a>, it calls <b>FreeAdapterChannel</b> to release the system DMA controller that was previously allocated with a call to <b>AllocateAdapterChannel</b>.

<b>FreeAdapterChannel</b> frees any map registers that were allocated by an earlier call to <b>AllocateAdapterChannel</b>. A driver calls this routine only if its <a href="https://msdn.microsoft.com/library/windows/hardware/ff540504">AdapterControl</a> routine returns <b>KeepObject</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **IRQL** | DISPATCH_LEVEL |
| **DDI compliance rules** | IrqlDispatch, IrqlDispatch(storport) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540573">AllocateAdapterChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545917">FlushAdapterBuffers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546513">FreeMapRegisters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554402">MapTransfer</a>