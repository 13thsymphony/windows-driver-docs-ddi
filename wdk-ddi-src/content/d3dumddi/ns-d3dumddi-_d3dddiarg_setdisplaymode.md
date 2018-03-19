---
UID: NS:d3dumddi._D3DDDIARG_SETDISPLAYMODE
title: "_D3DDDIARG_SETDISPLAYMODE"
author: windows-driver-content
description: The D3DDDIARG_SETDISPLAYMODE structure describes parameters for setting the display mode.
old-location: display\d3dddiarg_setdisplaymode.htm
old-project: display
ms.assetid: 4dd4c02f-af44-4b02-a646-b7648b430b89
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDIARG_SETDISPLAYMODE, D3DDDIARG_SETDISPLAYMODE structure [Display Devices], UMDisplayDriver_param_Structs_89fc526d-719f-43b5-b195-47a199a290ec.xml, _D3DDDIARG_SETDISPLAYMODE, d3dumddi/D3DDDIARG_SETDISPLAYMODE, display.d3dddiarg_setdisplaymode
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
-	D3DDDIARG_SETDISPLAYMODE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_SETDISPLAYMODE
---

# _D3DDDIARG_SETDISPLAYMODE structure
The D3DDDIARG_SETDISPLAYMODE structure describes parameters for setting the display mode.

## Syntax
````
typedef struct _D3DDDIARG_SETDISPLAYMODE {
  HANDLE hResource;
  UINT   SubResourceIndex;
} D3DDDIARG_SETDISPLAYMODE;
````

## Members


`hResource`

[in] A handle to the resource that contains the display surface.

`SubResourceIndex`

[in] The zero-based index into the resource, which is specified by the handle in the <b>hResource</b> member. This index indicates the display surface.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdisplaymode.md">SetDisplayMode</a>