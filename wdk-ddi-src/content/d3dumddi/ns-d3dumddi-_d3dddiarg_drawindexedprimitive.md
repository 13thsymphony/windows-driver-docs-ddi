---
UID: NS:d3dumddi._D3DDDIARG_DRAWINDEXEDPRIMITIVE
title: "_D3DDDIARG_DRAWINDEXEDPRIMITIVE"
author: windows-driver-content
description: The D3DDDIARG_DRAWINDEXEDPRIMITIVE structure describes an indexed primitive to draw.
old-location: display\d3dddiarg_drawindexedprimitive.htm
old-project: display
ms.assetid: 3f8cc918-9819-4c32-93f3-dbc2c1023016
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDIARG_DRAWINDEXEDPRIMITIVE, D3DDDIARG_DRAWINDEXEDPRIMITIVE structure [Display Devices], UMDisplayDriver_param_Structs_241177c0-f301-4b49-93cb-5c75ca8cb30a.xml, _D3DDDIARG_DRAWINDEXEDPRIMITIVE, d3dumddi/D3DDDIARG_DRAWINDEXEDPRIMITIVE, display.d3dddiarg_drawindexedprimitive
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
-	D3DDDIARG_DRAWINDEXEDPRIMITIVE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_DRAWINDEXEDPRIMITIVE
---

# _D3DDDIARG_DRAWINDEXEDPRIMITIVE structure
The D3DDDIARG_DRAWINDEXEDPRIMITIVE structure describes an indexed primitive to draw.

## Syntax
```
typedef struct _D3DDDIARG_DRAWINDEXEDPRIMITIVE {
  D3DPRIMITIVETYPE PrimitiveType;
  INT              BaseVertexIndex;
  UINT             MinIndex;
  UINT             NumVertices;
  UINT             StartIndex;
  UINT             PrimitiveCount;
} D3DDDIARG_DRAWINDEXEDPRIMITIVE;
```

## Members


`PrimitiveType`

[in] A D3DPRIMITIVETYPE-typed value that indicates the type of primitive to draw. This member can be one of the following values: D3DPT_POINTLIST, D3DPT_LINELIST, D3DPT_LINESTRIP, D3DPT_TRIANGLELIST, D3DPT_TRIANGLESTRIP, or D3DPT_TRIANGLEFAN. For more information about D3DPRIMITIVETYPE, see the Microsoft Windows SDK documentation.

`BaseVertexIndex`

[in] The number that should be added to each index that is referenced by the various primitives to determine the actual index of the vertex elements in each vertex stream.

`MinIndex`

[in] The minimum index of a range of vertices that are potentially accessed by the primitives to be drawn and, therefore, which vertices should be processed.

`NumVertices`

[in] The number of vertices in a range that are potentially accessed by the primitives to be drawn and, therefore, which vertices should be processed.

`StartIndex`

[in] The first index in the index buffer from which indices are read to draw the primitives.

`PrimitiveCount`

[in] The number of triangles, lines, or points to draw for the given primitive.

## Remarks
The Microsoft Direct3D runtime does not transform the index data before passing a pointer to the description of the index data in the <i>pData</i> parameter in a call to the user-mode display driver's <a href="https://msdn.microsoft.com/12bb6274-d042-43bb-b9f5-1417f42da729">DrawIndexedPrimitive</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/12bb6274-d042-43bb-b9f5-1417f42da729">DrawIndexedPrimitive</a>