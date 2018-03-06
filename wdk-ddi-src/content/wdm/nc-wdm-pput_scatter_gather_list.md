---
UID: NC:wdm.PPUT_SCATTER_GATHER_LIST
title: PPUT_SCATTER_GATHER_LIST
author: windows-driver-content
description: The PutScatterGatherList routine frees the previously allocated map registers and scatter/gather list used in scatter/gather DMA.
old-location: kernel\putscattergatherlist.htm
old-project: kernel
ms.assetid: e10091c0-0da6-4acd-8104-9d353262836a
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PPUT_SCATTER_GATHER_LIST, PutScatterGatherList, PutScatterGatherList callback function [Kernel-Mode Driver Architecture], kdma_0f73e6d3-bf6c-4f2b-aff9-ae783b2130c5.xml, kernel.putscattergatherlist, ntddk/PutScatterGatherList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows. Not supported in Windows 98 or Windows Me.
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
-	ntddk.h
api_name:
-	PutScatterGatherList
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---


# PPUT_SCATTER_GATHER_LIST callback function
The <b>PutScatterGatherList</b> routine frees the previously allocated map registers and scatter/gather list used in scatter/gather DMA.

## Syntax

```
PPUT_SCATTER_GATHER_LIST PputScatterGatherList;

void PputScatterGatherList(
  PDMA_ADAPTER DmaAdapter,
  PSCATTER_GATHER_LIST ScatterGather,
  BOOLEAN WriteToDevice
)
{...}
```

## Parameters

`DmaAdapter`

Pointer to the <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure returned by <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.

`ScatterGather`

Pointer to a <a href="..\wdm\ns-wdm-_scatter_gather_list.md">SCATTER_GATHER_LIST</a> structure previously returned by <a href="..\wdm\nc-wdm-pget_scatter_gather_list.md">GetScatterGatherList</a>.

`WriteToDevice`

Indicates the direction of the DMA transfer: specify <b>TRUE</b> for a transfer from the buffer to the device, and <b>FALSE</b> otherwise.


## Return Value

None

## Remarks

<b>PutScatterGatherList</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>.

Drivers should call <b>PutScatterGatherList</b> after completing scatter/gather I/O. This routine flushes the adapter buffers, frees the map registers, and unmaps and frees the associated MDLs. Additionally, the routine frees the scatter/gather list if it was previously allocated by <a href="..\wdm\nc-wdm-pget_scatter_gather_list.md">GetScatterGatherList</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of Windows. Not supported in Windows 98 or Windows Me.  |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **IRQL** | DISPATCH_LEVEL |
| **DDI compliance rules** | IrqlDispatch, IrqlDispatch(storport) |

## See Also

<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>



<a href="..\wdm\ns-wdm-_scatter_gather_list.md">SCATTER_GATHER_LIST</a>



<a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>



<a href="..\wdm\nc-wdm-pget_scatter_gather_list.md">GetScatterGatherList</a>



<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PPUT_SCATTER_GATHER_LIST callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>