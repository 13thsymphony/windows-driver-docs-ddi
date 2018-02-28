---
UID: NC:wdm.PFREE_MAP_REGISTERS
title: PFREE_MAP_REGISTERS
author: windows-driver-content
description: The FreeMapRegisters routine releases a set of map registers that were saved from a call to AllocateAdapterChannel.
old-location: kernel\freemapregisters.htm
old-project: kernel
ms.assetid: 0326229f-cf02-4368-bc32-7fbed118714b
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: FreeMapRegisters, FreeMapRegisters callback function [Kernel-Mode Driver Architecture], PFREE_MAP_REGISTERS, kdma_039f59c4-101e-40c2-bf2e-a0faa7c11032.xml, kernel.freemapregisters, wdm/FreeMapRegisters
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
-	FreeMapRegisters
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---


# PFREE_MAP_REGISTERS callback function
The <b>FreeMapRegisters</b> routine releases a set of map registers that were saved from a call to <a href="..\wdm\nc-wdm-pallocate_adapter_channel.md">AllocateAdapterChannel</a>.

## Syntax

```
PFREE_MAP_REGISTERS PfreeMapRegisters;

void PfreeMapRegisters(
  PDMA_ADAPTER DmaAdapter,
  PVOID MapRegisterBase,
  ULONG NumberOfMapRegisters
)
{...}
```

## Parameters

`DmaAdapter`

Pointer to the <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure returned by <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.

`MapRegisterBase`

Specifies the map registers allocated for the DMA operation.  The system passes this value  to the driver's <a href="..\wdm\nc-wdm-driver_control.md">AdapterControl</a> routine.

`NumberOfMapRegisters`

Specifies the number of map registers to be released. This value must match the number specified in an earlier call to <a href="..\wdm\nc-wdm-pallocate_adapter_channel.md">AllocateAdapterChannel</a>.


## Return Value

None

## Remarks

<b>FreeMapRegisters</b>
           is not a system routine that can be called directly by name. This routine is only callable by pointer from the address returned in a 
          <a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>.

When the driver of a bus-master device has completed the current packet-based DMA transfer request, it calls <b>FreeMapRegisters</b> to release the map registers previously allocated by a call to <a href="..\wdm\nc-wdm-pallocate_adapter_channel.md">AllocateAdapterChannel</a> and retained because its <i>AdapterControl</i> routine returned <b>DeallocateObjectKeepRegisters</b>. The driver must call <b>FreeMapRegisters</b> after calling <a href="..\wdm\nc-wdm-pflush_adapter_buffers.md">FlushAdapterBuffers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **IRQL** | DISPATCH_LEVEL |
| **DDI compliance rules** | IrqlDispatch, IrqlDispatch(storport) |

## See Also

<a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>



<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>



<a href="..\wdm\nc-wdm-pmap_transfer.md">MapTransfer</a>



<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>



<a href="..\wdm\nc-wdm-pallocate_adapter_channel.md">AllocateAdapterChannel</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PFREE_MAP_REGISTERS callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>