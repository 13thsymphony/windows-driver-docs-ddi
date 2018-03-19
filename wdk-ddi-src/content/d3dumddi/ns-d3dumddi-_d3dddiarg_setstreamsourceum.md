---
UID: NS:d3dumddi._D3DDDIARG_SETSTREAMSOURCEUM
title: "_D3DDDIARG_SETSTREAMSOURCEUM"
author: windows-driver-content
description: The D3DDDIARG_SETSTREAMSOURCEUM structure describes the vertex stream to bind to a user-memory buffer.
old-location: display\d3dddiarg_setstreamsourceum.htm
old-project: display
ms.assetid: 1406f6d7-7da9-4c1a-93c5-384b13fa5e81
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDIARG_SETSTREAMSOURCEUM, D3DDDIARG_SETSTREAMSOURCEUM structure [Display Devices], UMDisplayDriver_param_Structs_783c5264-b293-4ddc-b269-c1cd3a66d431.xml, _D3DDDIARG_SETSTREAMSOURCEUM, d3dumddi/D3DDDIARG_SETSTREAMSOURCEUM, display.d3dddiarg_setstreamsourceum
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
-	D3DDDIARG_SETSTREAMSOURCEUM
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_SETSTREAMSOURCEUM
---

# _D3DDDIARG_SETSTREAMSOURCEUM structure
The D3DDDIARG_SETSTREAMSOURCEUM structure describes the vertex stream to bind to a user-memory buffer.

## Syntax
````
typedef struct _D3DDDIARG_SETSTREAMSOURCEUM {
  UINT Stream;
  UINT Stride;
} D3DDDIARG_SETSTREAMSOURCEUM;
````

## Members


`Stream`

[in] The index, starting from zero, for the vertex stream to bind to a user-memory buffer.

`Stride`

[in] The size, in bytes, from one vertex to the next vertex in the stream. In contrast to the call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setstreamsource.md">SetStreamSource</a> function, <b>Stride</b> cannot be set to zero. Because only one stream can be bound to a user memory buffer, each vertex in the stream must receive different data for processing.

The <b>Stride</b> value must be DWORD-aligned.

## Remarks
In a call to the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setstreamsourceum.md">SetStreamSourceUM</a> function, a pointer to a D3DDDIARG_SETSTREAMSOURCEUM structure is passed in the <i>pData</i> parameter. The Microsoft Direct3D runtime supplies vertex data for the vertex stream through the <i>pUMBuffer</i> parameter in a call to the user-mode display driver's <b>SetStreamSourceUM</b> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setstreamsourceum.md">SetStreamSourceUM</a>