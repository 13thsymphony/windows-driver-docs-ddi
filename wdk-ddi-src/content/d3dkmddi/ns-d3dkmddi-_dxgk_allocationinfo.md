---
UID: NS:d3dkmddi._DXGK_ALLOCATIONINFO
title: "_DXGK_ALLOCATIONINFO"
author: windows-driver-content
description: The DXGK_ALLOCATIONINFO structure describes parameters for creating an allocation.
old-location: display\dxgk_allocationinfo.htm
old-project: display
ms.assetid: d5767bd3-11f8-45a7-b760-3ed51c54c044
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_ALLOCATIONINFO, DXGK_ALLOCATIONINFO structure [Display Devices], DmStructs_f571b666-75fd-477a-a8a7-673033d9284e.xml, _DXGK_ALLOCATIONINFO, d3dkmddi/DXGK_ALLOCATIONINFO, display.dxgk_allocationinfo
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
-	DXGK_ALLOCATIONINFO
product: Windows
targetos: Windows
req.typenames: DXGK_ALLOCATIONINFO
---

# _DXGK_ALLOCATIONINFO structure
The DXGK_ALLOCATIONINFO structure describes parameters for creating an allocation.

## Syntax
```
typedef struct _DXGK_ALLOCATIONINFO {
  VOID                       *pPrivateDriverData;
  UINT                       PrivateDriverDataSize;
  UINT                       Alignment;
  SIZE_T                     Size;
  SIZE_T                     PitchAlignedSize;
  DXGK_SEGMENTBANKPREFERENCE HintedBank;
  DXGK_SEGMENTPREFERENCE     PreferredSegment;
  UINT                       SupportedReadSegmentSet;
  UINT                       SupportedWriteSegmentSet;
  UINT                       EvictionSegmentSet;
  union {
    UINT MaximumRenamingListLength;
    UINT PhysicalAdapterIndex;
  };
  HANDLE                     hAllocation;
  union {
    DXGK_ALLOCATIONINFOFLAGS         Flags;
    DXGK_ALLOCATIONINFOFLAGS_WDDM2_0 FlagsWddm2;
  };
  DXGK_ALLOCATIONUSAGEHINT   *pAllocationUsageHint;
  UINT                       AllocationPriority;
} DXGK_ALLOCATIONINFO;
```

## Members


`pPrivateDriverData`

[in] A pointer to a block of private data. This data is for each allocation and is distinct from the <b>pPrivateDriverData</b> member in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557559">DXGKARG_CREATEALLOCATION</a> structure. The user-mode display driver might pass this data to the display miniport driver. However, if  the Microsoft DirectX graphics kernel subsystem passes this data to describe the shared primary or other lockable surface, the data is passed as the first element of the array in the <b>pAllocationInfo</b> member of DXGKARG_CREATEALLOCATION.

`PrivateDriverDataSize`

[in] The size, in bytes, of the block of private data in <b>pPrivateDriverData</b>.

`Alignment`

[out] The required alignment, in bytes, for the allocation.

`Size`

[out] The size, in bytes, that is required for the allocation. The size value is expanded to a multiple of the native host page size (for example, 4 KB on the x86 architecture). The display miniport driver specifies the allocation size to the video memory manager.

`PitchAlignedSize`

[out] The size, in bytes, of the allocation when it is located in a pitch-aligned segment, which is specified by the <b>PitchAlignment</b> bit-field flag in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562035">DXGK_SEGMENTDESCRIPTOR</a> structure for the segment. If the allocation is not supported in a pitch-aligned segment (graphics processing units [GPUs] commonly do not support this type of segment), the driver should set the value in <b>PitchAlignedSize</b> to zero. If the driver specifies a nonzero value in <b>PitchAlignedSize</b>, the value must be greater than or equal to the value in the <b>Size</b> member.

`HintedBank`

[out] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff562032">DXGK_SEGMENTBANKPREFERENCE</a> structure that indicates the bank ordering preferences that the display miniport driver requests that the video memory manager use to page-in the allocation. If this member is specified, the video memory manager uses banking information about the most preferred segment, which is specified by the <b>SegmentId0</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562047">DXGK_SEGMENTPREFERENCE</a> structure that the <b>PreferredSegment</b> member specifies.

`PreferredSegment`

[out] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff562047">DXGK_SEGMENTPREFERENCE</a> structure that indicates preferred segments identifiers that the display miniport driver requests that the video memory manager use to page-in the allocation.

`SupportedReadSegmentSet`

[out] Segment identifiers that the display miniport driver can set in the <b>PreferredSegment</b> member for read operations. The segments that these identifiers indicate are segments that the display miniport driver requests that the video memory manager use to page-in the allocation for read operations, regardless of performance. Setting bit 0 indicates that the first segment is supported, setting bit 1 indicates that the second segment is supported, and so on. 

The display miniport driver can set preferences only for segments that are supported for read operations. The video memory manager asserts if the driver attempts to set preferences for unsupported segments in the <b>PreferredSegment</b> member.

`SupportedWriteSegmentSet`

[out] Segment identifiers that the display miniport driver can set in the <b>PreferredSegment</b> member for write operations. The segments that these identifiers indicate are segments that the display miniport driver requests that the video memory manager use to page-in the allocation for write operations, regardless of performance. Setting bit 0 indicates that the first segment is supported, setting bit 1 indicates that the second segment is supported, and so on. 

The display miniport driver can set preferences only for segments that are supported for write operations. The video memory manager asserts if the driver attempts to set preferences for unsupported segments in the <b>PreferredSegment</b> member.

`EvictionSegmentSet`

[out] Identifiers of segments that can be used for eviction. Setting bit 0 indicates that the first segment can be used for eviction, setting bit 1 indicates that the second segment can be used for eviction, and so on. 

Only aperture segments can be specified by this member. If the driver specifies valid segments to be used for eviction, the video memory manager attempts to allocate resources in those aperture segments to accelerate the eviction process. If the driver specifies 0, the video memory manager calls the driver to transfer the content of an allocation directly to paged-locked system memory without mapping the underlying pages through an aperture segment.

`hAllocation`

[out] A handle to the allocation. The display miniport driver must set this member to a value that it can use to refer to its private tracking structure for the allocation.

`pAllocationUsageHint`

[out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560981">DXGK_ALLOCATIONUSAGEHINT</a> structure that the memory manager uses to determine how to use the allocation.

`AllocationPriority`

[out] A UINT value that specifies the starting priority level of the allocation. 

The driver determines the appropriate priority level for each allocation. For more information about priority levels, see the Remarks section of the <a href="https://msdn.microsoft.com/1812cb0f-9232-4813-9c7b-74c9fa4d03cf">pfnSetPriorityCb</a> function. If priority level for allocations is not an issue to the driver, the driver should set all priority levels to <b>D3DDDI_ALLOCATIONPRIORITY_NORMAL</b>. Note that 0 is an invalid initial allocation priority.

## Remarks
With the WDDM v2, the <b>DXGK_ALLOCATIONINFO</b> structure has been changed so that the read and write segment set are no longer differentiated. During surface creation the video memory manager will ignore the <b>SupportedReadSegmentSet</b> value and use only the segment set provide by <b>SupportedWriteSegmentSet</b>. Drivers should ensure that this value accurately represents the segment set that can be used by the allocation for its intended purpose.


Ignoring the supported read segment set does not mean that it is no longer supported, but simply that there should no longer be a difference between these sets, and the video memory manager will be allowed to choose an appropriate segment for any allocation from a single segment set.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="https://msdn.microsoft.com/edf59add-0155-4619-9c7c-fdb63b954f85">D3DKMDDI_SHAREDPRIMARYSURFACEDATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557559">DXGKARG_CREATEALLOCATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560966">DXGK_ALLOCATIONINFOFLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560975">DXGK_ALLOCATIONLIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560981">DXGK_ALLOCATIONUSAGEHINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562032">DXGK_SEGMENTBANKPREFERENCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562035">DXGK_SEGMENTDESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562047">DXGK_SEGMENTPREFERENCE</a>



<a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>



<a href="https://msdn.microsoft.com/fd634768-5e1e-4f40-82fd-5ef69148c3d7">DxgkDdiRender</a>



<a href="https://msdn.microsoft.com/a61e6c6a-3992-429c-ad8c-5f1a61dc7b8b">pfnAllocateCb</a>