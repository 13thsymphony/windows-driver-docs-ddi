---
UID: NS:d3dumddi._D3DDDIARG_SETRENDERTARGET
title: "_D3DDDIARG_SETRENDERTARGET"
author: windows-driver-content
description: The D3DDDIARG_SETRENDERTARGET structure describes the render target surface.
old-location: display\d3dddiarg_setrendertarget.htm
old-project: display
ms.assetid: 88b0de48-1b85-4733-809c-6d8da657e920
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDIARG_SETRENDERTARGET, D3DDDIARG_SETRENDERTARGET structure [Display Devices], UMDisplayDriver_param_Structs_42cfb4bf-f5af-4008-9c6d-062e910b3238.xml, _D3DDDIARG_SETRENDERTARGET, d3dumddi/D3DDDIARG_SETRENDERTARGET, display.d3dddiarg_setrendertarget
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
-	D3DDDIARG_SETRENDERTARGET
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_SETRENDERTARGET
---

# _D3DDDIARG_SETRENDERTARGET structure
The D3DDDIARG_SETRENDERTARGET structure describes the render target surface.

## Syntax
````
typedef struct _D3DDDIARG_SETRENDERTARGET {
  UINT   RenderTargetIndex;
  HANDLE hRenderTarget;
  UINT   SubResourceIndex;
} D3DDDIARG_SETRENDERTARGET;
````

## Members


`RenderTargetIndex`

[in] An index into the group of render target surfaces.

`hRenderTarget`

[in] A handle to the render target surface or the group of render target surfaces.

`SubResourceIndex`

[in] An index into the resource for the render target.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setrendertarget.md">SetRenderTarget</a>