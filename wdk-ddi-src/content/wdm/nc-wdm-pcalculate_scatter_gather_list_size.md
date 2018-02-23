---
UID: NC:wdm.PCALCULATE_SCATTER_GATHER_LIST_SIZE
title: PCALCULATE_SCATTER_GATHER_LIST_SIZE
author: windows-driver-content
description: The CalculateScatterGatherList routine calculates the size, in bytes, of scatter/gather list necessary to hold a given buffer.
old-location: kernel\calculatescattergatherlist.htm
old-project: kernel
ms.assetid: d7509502-0965-44b9-8efb-cec4fbe3ac88
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.calculatescattergatherlist, CalculateScatterGatherList, CalculateScatterGatherList callback function [Kernel-Mode Driver Architecture], CalculateScatterGatherList, PCALCULATE_SCATTER_GATHER_LIST_SIZE, PCALCULATE_SCATTER_GATHER_LIST_SIZE, wdm/CalculateScatterGatherList, kdma_f2e8ba68-4b5d-4a3c-9e81-1bf84cc7cc48.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	wdm.h
apiname:
-	CalculateScatterGatherList
product: Windows
targetos: Windows
req.typenames: "*PWDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME"
req.product: Windows 10 or later.
---


# PCALCULATE_SCATTER_GATHER_LIST_SIZE callback function
The <b>CalculateScatterGatherList</b> routine calculates the size, in bytes, of scatter/gather list necessary to hold a given buffer.

## Syntax

```
PCALCULATE_SCATTER_GATHER_LIST_SIZE PcalculateScatterGatherListSize;

NTSTATUS PcalculateScatterGatherListSize(
  PDMA_ADAPTER DmaAdapter,
  OPTIONAL PMDL Mdl,
  PVOID CurrentVa,
  ULONG Length,
  PULONG ScatterGatherListSize,
  OPTIONAL PULONG pNumberOfMapRegisters
)
{...}
```

## Parameters

`DmaAdapter`

Pointer to the <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure returned by <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.

`Mdl`

Either <b>NULL</b> or a pointer to the MDL that contains the buffer.

`CurrentVa`

Pointer to the virtual address of the beginning of the buffer.

`Length`

Specifies the length of the buffer, in bytes.

`ScatterGatherListSize`

Pointer to the variable the routine uses to return the size of the scatter/gather list, in bytes.

`pNumberOfMapRegisters`




## Return Value

<b>CalculateScatterGatherList</b> returns one of the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The values returned in <i>ScatterGatherListSize</i> and <i>NumberOfMapRegisters</i> are valid. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The number of map registers required exceeds the number of map registers available. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>Length</i> is too big to fit within the buffer. 

</td>
</tr>
</table>

## Remarks

<b>CalculateScatterGatherList</b>
      is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a 
     <a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>
      structure. Drivers obtain the address of this routine by calling <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION2. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

If the caller passes <b>NULL</b> for the <i>Mdl</i> parameter, the routine calculates the maximum possible size needed to hold a scatter/gather list for the specified buffer. If the caller specifies the MDL that contains the buffer in the <i>Mdl</i> parameter, the routine computes the actual size needed to hold the scatter/gather list.

A driver uses <b>CalculateScatterGatherList</b> to allocate a scatter/gather list buffer to pass to <a href="..\wdm\nc-wdm-pbuild_scatter_gather_list.md">BuildScatterGatherList</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of Windows.  |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h) |
| **IRQL** | Any level |

## See Also

<a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>



<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>



<a href="..\wdm\nc-wdm-pbuild_scatter_gather_list.md">BuildScatterGatherList</a>



<a href="..\wdm\ns-wdm-_scatter_gather_list.md">SCATTER_GATHER_LIST</a>



<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>



<a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PCALCULATE_SCATTER_GATHER_LIST_SIZE callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>