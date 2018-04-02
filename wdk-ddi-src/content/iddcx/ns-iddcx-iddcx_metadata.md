---
UID: NS:iddcx.IDDCX_METADATA
title: IDDCX_METADATA
author: windows-driver-content
description: Gives information about the current provided surface and what is displayed on it.
old-location: display\iddcx_metadata.htm
old-project: display
ms.assetid: 7128e49d-71e9-4014-9f08-591cfaeba363
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IDDCX_METADATA, IDDCX_METADATA structure, IDDCX_METADATA structure [Display Devices], IDDCX_METADATA structure pointer [Display Devices], IDDCX_METADATA structure structure [Display Devices], display.iddcx_metadata, iddcx/IDDCX_METADATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iddcx.h
api_name:
-	IDDCX_METADATA
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDDCX_METADATA structure
Gives information about the current provided surface and what is displayed on it.

## Syntax
```
struct IDDCX_METADATA {
  UINT          Size;
  UINT          PresentationFrameNumber;
  UINT          DirtyRectCount;
  UINT          MoveRegionCount;
  BOOL          HwProtectedSurface;
  UINT64        PresentDisplayQPCTime;
  IDXGIResource *pSurface;
};
```

## Members


`Size`

Total size of the structure

`PresentationFrameNumber`

Presentation frame number of this surface. If the frame number is the same as the previous frame, then it indicates that there has not been any image updates from the previous frame. This is an opportunity for the driver to re-encode the desktop image again to increase the visual quality. Once there are no more updates, the OS presents the same frame as many times indicated by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt761932">IDDCX_ADAPTER_CAPS</a> value <b>StaticDesktopReencodeFrameCount</b> , then stops presenting until the next update

`DirtyRectCount`

Number of dirty rects for this frame. Call <a href="https://msdn.microsoft.com/library/windows/hardware/mt761927">IddCxSwapChainGetDirtyRects</a> to get the dirty rects
                 

<div class="alert"><b>Note</b>   A zero <b>DirtyRectCount</b> and <b>MoveRegionCount</b> value indicates there were no desktop updates and the
    PresentationFrameNumber is the same as last frame</div>
<div> </div>

`MoveRegionCount`

Number of move regions in this frame, call <a href="https://msdn.microsoft.com/library/windows/hardware/mt761928">IddCxSwapChainGetMoveRegions</a> to get the move regions
                 

<div class="alert"><b>Note</b>   A zero <b>DirtyRectCount</b> and <b>MoveRegionCount</b> value indicates there were no desktop updates and the
    PresentationFrameNumber is the same as last frame</div>
<div> </div>

`HwProtectedSurface`

Indicates if the provided surface is hardware protected or not

`PresentDisplayQPCTime`

System QPC time of when this surface should be displayed on the indirect display monitor

`pSurface`

DX surface that contains the image to encode and transmit. The driver can use this DX surface anytime until <a href="https://msdn.microsoft.com/f9b0cf3f-cbb6-4b44-81c1-b60ae525ec17">IddCxSwapChainReleaseAndAcquire</a> is called again

<div class="alert"><b>Note</b>  This surface is always a A8R8G8B8 formated surface</div>
<div> </div>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iddcx.h |