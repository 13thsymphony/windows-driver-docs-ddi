---
UID: NC:wdm.PFREE_COMMON_BUFFER
title: PFREE_COMMON_BUFFER
author: windows-driver-content
description: The FreeCommonBuffer routine frees a common buffer allocated by AllocateCommonBuffer, along with all resources the buffer uses.
old-location: kernel\freecommonbuffer.htm
old-project: kernel
ms.assetid: 9e026bde-657a-42ea-907c-71cc217dbd8d
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: FreeCommonBuffer, FreeCommonBuffer callback function [Kernel-Mode Driver Architecture], PFREE_COMMON_BUFFER, kdma_73f76fbd-2641-4002-90c8-ca412e969418.xml, kernel.freecommonbuffer, wdm/FreeCommonBuffer
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
req.ddi-compliance: IrqlDispatch
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wdm.h
api_name:
-	FreeCommonBuffer
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---


# PFREE_COMMON_BUFFER callback function
The <b>FreeCommonBuffer</b> routine frees a common buffer allocated by <a href="..\wdm\nc-wdm-pallocate_common_buffer.md">AllocateCommonBuffer</a>, along with all resources the buffer uses.

## Syntax

```
PFREE_COMMON_BUFFER PfreeCommonBuffer;

void PfreeCommonBuffer(
  PDMA_ADAPTER DmaAdapter,
  ULONG Length,
  PHYSICAL_ADDRESS LogicalAddress,
  PVOID VirtualAddress,
  BOOLEAN CacheEnabled
)
{...}
```

## Parameters

`DmaAdapter`

Pointer to the <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure returned by <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.

`Length`

Specifies the number of bytes to deallocate.

`LogicalAddress`

Specifies the logical address of the allocated memory range.

`VirtualAddress`

Pointer to the corresponding virtual address of the allocated memory range.

`CacheEnabled`

Indicates whether the allocated memory is cached.


## Return Value

None

## Remarks

<b>FreeCommonBuffer</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>.

To release a common buffer, a driver calls <b>FreeCommonBuffer</b> to unmap both its logical and virtual addresses. The parameters passed to <b>FreeCommonBuffer</b> must match exactly those passed to and returned from <a href="..\wdm\nc-wdm-pallocate_common_buffer.md">AllocateCommonBuffer</a>. A driver cannot free part of an allocated common buffer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | IrqlDispatch |

## See Also

<a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>



<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>



<a href="..\wdm\nc-wdm-pallocate_common_buffer.md">AllocateCommonBuffer</a>



<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>