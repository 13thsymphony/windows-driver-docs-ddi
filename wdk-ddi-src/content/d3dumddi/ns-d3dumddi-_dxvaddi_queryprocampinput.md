---
UID: NS:d3dumddi._DXVADDI_QUERYPROCAMPINPUT
title: "_DXVADDI_QUERYPROCAMPINPUT"
author: windows-driver-content
description: The DXVADDI_QUERYPROCAMPINPUT structure describes a ProcAmp control property on a video stream that range information is requested for.
old-location: display\dxvaddi_queryprocampinput.htm
old-project: display
ms.assetid: 9ba7c42a-4140-4d8c-abb3-ae5f9285dbd9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXVA2_Structs_64cd50ed-940a-46a1-8a4d-b43d40e85b25.xml, DXVADDI_QUERYPROCAMPINPUT, DXVADDI_QUERYPROCAMPINPUT structure [Display Devices], _DXVADDI_QUERYPROCAMPINPUT, d3dumddi/DXVADDI_QUERYPROCAMPINPUT, display.dxvaddi_queryprocampinput
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
-	DXVADDI_QUERYPROCAMPINPUT
product: Windows
targetos: Windows
req.typenames: DXVADDI_QUERYPROCAMPINPUT
---

# _DXVADDI_QUERYPROCAMPINPUT structure
The DXVADDI_QUERYPROCAMPINPUT structure describes a ProcAmp control property on a video stream that range information is requested for.

## Syntax
```
typedef struct _DXVADDI_QUERYPROCAMPINPUT {
  CONST GUID        *pVideoProcGuid;
  DXVADDI_VIDEODESC VideoDesc;
  D3DDDIFORMAT      RenderTargetFormat;
  UINT              ProcAmpCap;
} DXVADDI_QUERYPROCAMPINPUT;
```

## Members


`pVideoProcGuid`

[in] A pointer to a GUID that represents the video processing device type.

`VideoDesc`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff562944">DXVADDI_VIDEODESC</a> structure that describes the video stream.

`RenderTargetFormat`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the render target for the video processing device.

`ProcAmpCap`

[in] A ProcAmp control property that range information is requested for. The ProcAmp control property can be one of the members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562917">DXVADDI_PROCAMPVALUES</a> structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543148">D3DDDIARG_GETCAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544132">D3DDDICAPS_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562917">DXVADDI_PROCAMPVALUES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562939">DXVADDI_VALUERANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562944">DXVADDI_VIDEODESC</a>



<a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a>