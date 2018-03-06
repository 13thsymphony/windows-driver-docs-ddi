---
UID: NC:d3dumddi.PFND3DDDI_DRAWPRIMITIVE2
title: PFND3DDDI_DRAWPRIMITIVE2
author: windows-driver-content
description: The DrawPrimitive2 function draws nonindexed primitives in which the Microsoft Direct3D runtime has transformed the vertex data.
old-location: display\drawprimitive2.htm
old-project: display
ms.assetid: a81080f0-fbb3-4616-9324-642b60befcb3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DrawPrimitive2, DrawPrimitive2 callback function [Display Devices], PFND3DDDI_DRAWPRIMITIVE2, UserModeDisplayDriver_Functions_5c08f7ff-b74c-4389-9b35-2f24f9468b5d.xml, d3dumddi/DrawPrimitive2, display.drawprimitive2
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
-	DrawPrimitive2
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_DRAWPRIMITIVE2 callback function
The <b>DrawPrimitive2</b> function draws nonindexed primitives in which the Microsoft Direct3D runtime has transformed the vertex data.

## Syntax

```
PFND3DDDI_DRAWPRIMITIVE2 Pfnd3dddiDrawprimitive2;

HRESULT Pfnd3dddiDrawprimitive2(
  HANDLE hDevice,
  CONST D3DDDIARG_DRAWPRIMITIVE2 *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<b>DrawPrimitive2</b> returns S_OK or an appropriate error result if the primitive is not successfully drawn.

## Remarks

Stream zero contains transform vertices and is the only stream that should be accessed.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_drawprimitive2.md">D3DDDIARG_DRAWPRIMITIVE2</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DRAWPRIMITIVE2 callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>