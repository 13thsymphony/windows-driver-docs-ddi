---
UID: NC:d3dumddi.PFND3DDDI_DRAWPRIMITIVE
title: PFND3DDDI_DRAWPRIMITIVE
author: windows-driver-content
description: The DrawPrimitive function draws nonindexed primitives in which the Microsoft Direct3D runtime has not transformed the vertex data.
old-location: display\drawprimitive.htm
old-project: display
ms.assetid: 1a6de2b0-cab0-4fcf-be1b-a8cc1c1f79e9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DrawPrimitive, DrawPrimitive callback function [Display Devices], PFND3DDDI_DRAWPRIMITIVE, UserModeDisplayDriver_Functions_c433d1f5-68ca-4461-a409-4353d8a581d8.xml, d3dumddi/DrawPrimitive, display.drawprimitive
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
-	D3dumddi.h
api_name:
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

When the Microsoft Direct3D runtime specifies triangle-edge flags in the value that the <i>pFlagBuffer</i> parameter points to, the runtime also specifies to draw one or more triangles (that is, the runtime specifies the D3DPT_TRIANGLEFAN value in the <b>PrimitiveType</b> member and from 0x00000001 to 0xFFFFFFFF in the <b>PrimitiveCount</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543057">D3DDDIARG_DRAWPRIMITIVE</a> structure that the <i>pData</i> parameter points to).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543057">D3DDDIARG_DRAWPRIMITIVE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>