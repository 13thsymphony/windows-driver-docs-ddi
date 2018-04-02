---
UID: NS:d3dumddi._D3DDDIARG_SETCLIPPLANE
title: "_D3DDDIARG_SETCLIPPLANE"
author: windows-driver-content
description: The D3DDDIARG_SETCLIPPLANE structure describes a clip plane.
old-location: display\d3dddiarg_setclipplane.htm
old-project: display
ms.assetid: 94e942a4-de66-47a3-89bf-fbec2a408775
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDIARG_SETCLIPPLANE, D3DDDIARG_SETCLIPPLANE structure [Display Devices], UMDisplayDriver_param_Structs_3371265a-3cb5-4aee-b019-14ef454e9d6d.xml, _D3DDDIARG_SETCLIPPLANE, d3dumddi/D3DDDIARG_SETCLIPPLANE, display.d3dddiarg_setclipplane
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
-	D3DDDIARG_SETCLIPPLANE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_SETCLIPPLANE
---

# _D3DDDIARG_SETCLIPPLANE structure
The D3DDDIARG_SETCLIPPLANE structure describes a clip plane.

## Syntax
```
typedef struct _D3DDDIARG_SETCLIPPLANE {
  UINT  Index;
  FLOAT Plane[4];
} D3DDDIARG_SETCLIPPLANE;
```

## Members


`Index`

[in] The index of the clipping plane for which the plane equation coefficients are set.

`Plane`

[in] A four-element array of the coefficients A, B, C, and D, in that order, in the general plane equation for the clipping plane.

## Remarks
The general plane equation in standard form is A<i>x</i> + B<i>y</i> + C<i>z</i> + D<i>w</i> = 0. A point with homogeneous coordinates (<i>x</i>, <i>y</i>, <i>z</i>, <i>w</i>) is visible in the half-space of this plane if A<i>x</i> + B<i>y</i> + C<i>z</i> + D<i>w</i> &gt;= 0. Points that exist on or behind the clipping plane are clipped from the scene. That is, points for which A<i>x</i> + B<i>y</i> + C<i>z</i> + D<i>w</i> &lt; 0 are clipped.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/99edfc35-23a5-41e0-8705-7dffba564c10">SetClipPlane</a>