---
UID: NC:d3dumddi.PFND3DDDI_SETCLIPPLANE
title: PFND3DDDI_SETCLIPPLANE
author: windows-driver-content
description: The SetClipPlane function sets a clip plane.
old-location: display\setclipplane.htm
old-project: display
ms.assetid: 99edfc35-23a5-41e0-8705-7dffba564c10
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_SETCLIPPLANE, SetClipPlane, SetClipPlane callback function [Display Devices], UserModeDisplayDriver_Functions_695212ed-888d-40c9-8234-305373703b98.xml, d3dumddi/SetClipPlane, display.setclipplane
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	SetClipPlane
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_SETCLIPPLANE callback function
The <i>SetClipPlane</i> function sets a clip plane.

## Syntax

```
PFND3DDDI_SETCLIPPLANE Pfnd3dddiSetclipplane;

HRESULT Pfnd3dddiSetclipplane(
  HANDLE hDevice,
  CONST D3DDDIARG_SETCLIPPLANE *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<i>SetClipPlane</i> returns S_OK or an appropriate error result if the clip plane is not successfully set.

## Remarks

The coefficients that are passed to <i>SetClipPlane</i> in the <b>Plane</b> array of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setclipplane.md">D3DDDIARG_SETCLIPPLANE</a> structure that is pointed to by <i>pData </i>are used in the general plane equation. For more information about the general plane equation, see the Remarks section of <b>D3DDDIARG_SETCLIPPLANE</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setclipplane.md">D3DDDIARG_SETCLIPPLANE</a>