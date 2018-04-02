---
UID: NS:d3dkmddi._DXGK_QUERYSEGMENTOUT
title: "_DXGK_QUERYSEGMENTOUT"
author: windows-driver-content
description: The DXGK_QUERYSEGMENTOUT structure describes memory-segment information that the display miniport driver should return from a call to its DxgkDdiQueryAdapterInfo function.
old-location: display\dxgk_querysegmentout.htm
old-project: display
ms.assetid: df640b7a-865a-4a8b-94be-ebc60e44cf72
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_QUERYSEGMENTOUT, DXGK_QUERYSEGMENTOUT structure [Display Devices], DmStructs_69650838-cd41-4786-aa3c-b2617b7d97b4.xml, _DXGK_QUERYSEGMENTOUT, d3dkmddi/DXGK_QUERYSEGMENTOUT, display.dxgk_querysegmentout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_QUERYSEGMENTOUT
product: Windows
targetos: Windows
req.typenames: DXGK_QUERYSEGMENTOUT
---

# _DXGK_QUERYSEGMENTOUT structure
The DXGK_QUERYSEGMENTOUT structure describes memory-segment information that the display miniport driver should return from a call to its <a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a> function.

## Syntax
```
typedef struct _DXGK_QUERYSEGMENTOUT {
  UINT                   NbSegment;
  DXGK_SEGMENTDESCRIPTOR *pSegmentDescriptor;
  UINT                   PagingBufferSegmentId;
  UINT                   PagingBufferSize;
  UINT                   PagingBufferPrivateDataSize;
} DXGK_QUERYSEGMENTOUT;
```

## Members


`NbSegment`

[out] The number of memory segments that the driver supports.

`pSegmentDescriptor`

[out] An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff562035">DXGK_SEGMENTDESCRIPTOR</a> structures that the driver populates with information about the segments it supports. The size of the array is the value that <b>NbSegment</b> specifies.

`PagingBufferSegmentId`

[out] The identifier of the segment that the video memory manager should allocate the paging buffer from. This segment must be an aperture segment.

`PagingBufferSize`

[out] The size, in bytes, that the video memory manager should allocate for the paging buffer.

`PagingBufferPrivateDataSize`

[out] The size, in bytes, of the driver-resident private data structure that is associated with each paging buffer. Memory for this private data structure is allocated from nonpaged pool. If the driver specifies zero for <b>PagingBufferPrivateDataSize</b>, no memory is allocated for the private data structure.

The private data structure that is associated with a paging buffer is initialized to zero when the paging buffer is created. During the lifetime of the paging buffer, the video memory manager never accesses the private data structure that is associated with the paging buffer.

## Remarks
The video memory manager allocates a paging buffer either from an aperture segment (if the <b>PagingBufferSegmentId</b> member identifies the segment) or as a contiguous write-combined memory block (if <b>PagingBufferSegmentId</b> is set to 0). If <b>PagingBufferSegmentId</b> is set to 0, the graphics processing unit (GPU) must access direct memory access (DMA) buffers by using PCI cycles on systems where AGP transfers that occur outside the AGP aperture are not permitted.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557621">DXGKARG_QUERYADAPTERINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562015">DXGK_QUERYSEGMENTIN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562035">DXGK_SEGMENTDESCRIPTOR</a>



<a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a>