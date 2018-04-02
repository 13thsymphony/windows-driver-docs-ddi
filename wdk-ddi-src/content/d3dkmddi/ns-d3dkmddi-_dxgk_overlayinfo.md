---
UID: NS:d3dkmddi._DXGK_OVERLAYINFO
title: "_DXGK_OVERLAYINFO"
author: windows-driver-content
description: The DXGK_OVERLAYINFO structure describes parameters that are required to create or modify an overlay.
old-location: display\dxgk_overlayinfo.htm
old-project: display
ms.assetid: 7c2a7484-452f-4801-b650-3d8221740892
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_OVERLAYINFO, DXGK_OVERLAYINFO structure [Display Devices], DmStructs_232178f2-9a25-40aa-8604-0414128c1a91.xml, _DXGK_OVERLAYINFO, d3dkmddi/DXGK_OVERLAYINFO, display.dxgk_overlayinfo
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
-	DXGK_OVERLAYINFO
product: Windows
targetos: Windows
req.typenames: DXGK_OVERLAYINFO
---

# _DXGK_OVERLAYINFO structure
The DXGK_OVERLAYINFO structure describes parameters that are required to create or modify an overlay.

## Syntax
```
typedef struct _DXGK_OVERLAYINFO {
  HANDLE           hAllocation;
  PHYSICAL_ADDRESS PhysicalAddress;
  UINT             SegmentId;
  RECT             DstRect;
  RECT             SrcRect;
  VOID             *pPrivateDriverData;
  UINT             PrivateDriverDataSize;
} DXGK_OVERLAYINFO;
```

## Members


`hAllocation`

[in] A handle to the allocation to be displayed on the overlay.

`PhysicalAddress`

[in] The physical address, within the segment that <b>SegmentId</b> specifies, of the allocation to be displayed.

`SegmentId`

[in] The identifier of a segment in which the allocation is currently paged-in.

`DstRect`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that contains the overlay destination rectangle, in device coordinates.

`SrcRect`

[in] A RECT structure that contains the overlay source rectangle, in device coordinates.

`pPrivateDriverData`

[in] A pointer to a block of private data that is passed from the user-mode display driver to the display miniport driver.

`PrivateDriverDataSize`

[in] The size, in bytes, of the block of private data that <b>pPrivateDriverData</b> points to.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557572">DXGKARG_CREATEOVERLAY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559496">DXGKARG_UPDATEOVERLAY</a>



<a href="https://msdn.microsoft.com/1ccdd16d-fd76-4039-b538-86c77b4e8cbb">DxgkDdiCreateOverlay</a>



<a href="https://msdn.microsoft.com/b131dbb9-1e11-4d04-97cb-e15ec2b025c7">DxgkDdiUpdateOverlay</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>