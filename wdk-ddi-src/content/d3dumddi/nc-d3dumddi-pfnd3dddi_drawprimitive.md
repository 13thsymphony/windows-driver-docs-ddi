---
UID: NC:d3dumddi.PFND3DDDI_DRAWPRIMITIVE
title: PFND3DDDI_DRAWPRIMITIVE
author: windows-driver-content
description: The DrawPrimitive function draws nonindexed primitives in which the Microsoft Direct3D runtime has not transformed the vertex data.
old-location: display\drawprimitive.htm
old-project: display
ms.assetid: 1a6de2b0-cab0-4fcf-be1b-a8cc1c1f79e9
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.drawprimitive, DrawPrimitive callback function [Display Devices], DrawPrimitive, PFND3DDDI_DRAWPRIMITIVE, PFND3DDDI_DRAWPRIMITIVE, d3dumddi/DrawPrimitive, UserModeDisplayDriver_Functions_c433d1f5-68ca-4461-a409-4353d8a581d8.xml
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
-	D3dumddi.h
apiname:
-	DrawPrimitive
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_DRAWPRIMITIVE callback function
The <b>DrawPrimitive</b> function draws nonindexed primitives in which the Microsoft Direct3D runtime has not transformed the vertex data.

## Syntax

```
PFND3DDDI_DRAWPRIMITIVE Pfnd3dddiDrawprimitive;

HRESULT Pfnd3dddiDrawprimitive(
  HANDLE hDevice,
  CONST D3DDDIARG_DRAWPRIMITIVE *,
  CONST UINT *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`



`*`




## Return Value

<b>DrawPrimitive</b> returns S_OK or an appropriate error result if the primitive is not successfully drawn.

## Remarks

When the Microsoft Direct3D runtime specifies triangle-edge flags in the value that the <i>pFlagBuffer</i> parameter points to, the runtime also specifies to draw one or more triangles (that is, the runtime specifies the D3DPT_TRIANGLEFAN value in the <b>PrimitiveType</b> member and from 0x00000001 to 0xFFFFFFFF in the <b>PrimitiveCount</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_drawprimitive.md">D3DDDIARG_DRAWPRIMITIVE</a> structure that the <i>pData</i> parameter points to).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_drawprimitive.md">D3DDDIARG_DRAWPRIMITIVE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DRAWPRIMITIVE callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>