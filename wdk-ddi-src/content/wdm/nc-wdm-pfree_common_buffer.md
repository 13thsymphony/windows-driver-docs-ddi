---
UID : NC:wdm.PFREE_COMMON_BUFFER
title : PFREE_COMMON_BUFFER
author : windows-driver-content
description : The FreeCommonBuffer routine frees a common buffer allocated by AllocateCommonBuffer, along with all resources the buffer uses.
old-location : kernel\freecommonbuffer.htm
old-project : kernel
ms.assetid : 9e026bde-657a-42ea-907c-71cc217dbd8d
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : kernel.freecommonbuffer, FreeCommonBuffer, FreeCommonBuffer callback function [Kernel-Mode Driver Architecture], FreeCommonBuffer, PFREE_COMMON_BUFFER, PFREE_COMMON_BUFFER, wdm/FreeCommonBuffer, kdma_73f76fbd-2641-4002-90c8-ca412e969418.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Desktop
req.target-min-winverclnt : Available starting with Windows 2000.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : IrqlDispatch
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product : Windows 10 or later.
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

Pointer to the <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.

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
           structure. Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>.

To release a common buffer, a driver calls <b>FreeCommonBuffer</b> to unmap both its logical and virtual addresses. The parameters passed to <b>FreeCommonBuffer</b> must match exactly those passed to and returned from <a href="..\wdm\nc-wdm-pallocate_common_buffer.md">AllocateCommonBuffer</a>. A driver cannot free part of an allocated common buffer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | IrqlDispatch |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>

<a href="..\wdm\nc-wdm-pallocate_common_buffer.md">AllocateCommonBuffer</a>

<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>

<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PFREE_COMMON_BUFFER callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>