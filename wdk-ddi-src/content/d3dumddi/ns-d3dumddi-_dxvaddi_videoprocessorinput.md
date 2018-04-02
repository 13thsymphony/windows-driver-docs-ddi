---
UID: NS:d3dumddi._DXVADDI_VIDEOPROCESSORINPUT
title: "_DXVADDI_VIDEOPROCESSORINPUT"
author: windows-driver-content
description: The DXVADDI_VIDEOPROCESSORINPUT structure describes a video stream that is processed by a video processing device type.
old-location: display\dxvaddi_videoprocessorinput.htm
old-project: display
ms.assetid: 539d32a5-4566-4b8e-b9de-da8d5be3c2f2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXVA2_Structs_87cc7918-2fb5-4b73-a62c-ab9a3817c154.xml, DXVADDI_VIDEOPROCESSORINPUT, DXVADDI_VIDEOPROCESSORINPUT structure [Display Devices], _DXVADDI_VIDEOPROCESSORINPUT, d3dumddi/DXVADDI_VIDEOPROCESSORINPUT, display.dxvaddi_videoprocessorinput
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	DXVADDI_VIDEOPROCESSORINPUT
product: Windows
targetos: Windows
req.typenames: DXVADDI_VIDEOPROCESSORINPUT
---

# _DXVADDI_VIDEOPROCESSORINPUT structure
The DXVADDI_VIDEOPROCESSORINPUT structure describes a video stream that is processed by a video processing device type.

## Syntax
```
typedef struct _DXVADDI_VIDEOPROCESSORINPUT {
  CONST GUID        *pVideoProcGuid;
  DXVADDI_VIDEODESC VideoDesc;
  D3DDDIFORMAT      RenderTargetFormat;
} DXVADDI_VIDEOPROCESSORINPUT;
```

## Members


`pVideoProcGuid`

[in] A pointer to a GUID that represents the video processing device type.

`VideoDesc`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff562944">DXVADDI_VIDEODESC</a> structure that describes the video stream.

`RenderTargetFormat`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the render target for the video processing device.

## Remarks
When the D3DDDICAPS_GETVIDEOPROCESSORRTFORMATCOUNT, D3DDDICAPS_GETVIDEOPROCESSORRTFORMATS, D3DDDICAPS_GETVIDEOPROCESSORRTSUBSTREAMFORMATCOUNT, or D3DDDICAPS_GETVIDEOPROCESSORRTSUBSTREAMFORMATS <a href="https://msdn.microsoft.com/library/windows/hardware/ff544132">D3DDDICAPS_TYPE</a>-type value is sent in a call to the user-mode display driver's <a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a> function, the driver ignores the <b>RenderTargetFormat</b> member of DXVADDI_VIDEOPROCESSORINPUT.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543148">D3DDDIARG_GETCAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544132">D3DDDICAPS_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562944">DXVADDI_VIDEODESC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562953">DXVADDI_VIDEOPROCESSORCAPS</a>



<a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a>