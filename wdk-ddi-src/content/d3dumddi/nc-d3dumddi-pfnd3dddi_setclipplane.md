---
UID: NC:d3dumddi.PFND3DDDI_SETCLIPPLANE
title: PFND3DDDI_SETCLIPPLANE
author: windows-driver-content
description: The SetClipPlane function sets a clip plane.
old-location: display\setclipplane.htm
old-project: display
ms.assetid: 99edfc35-23a5-41e0-8705-7dffba564c10
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.setclipplane, SetClipPlane callback function [Display Devices], SetClipPlane, PFND3DDDI_SETCLIPPLANE, PFND3DDDI_SETCLIPPLANE, d3dumddi/SetClipPlane, UserModeDisplayDriver_Functions_695212ed-888d-40c9-8234-305373703b98.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
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

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setclipplane.md">D3DDDIARG_SETCLIPPLANE</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETCLIPPLANE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>