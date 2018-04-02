---
UID: NS:d3dhal._D3DHAL_DP2SETTRANSFORM
title: "_D3DHAL_DP2SETTRANSFORM"
author: windows-driver-content
description: D3DHAL_DP2SETTRANSFORM structure is used to specify the transform state and matrix for D3dDrawPrimitives2.
old-location: display\d3dhal_dp2settransform.htm
old-project: display
ms.assetid: 7905f5bd-15f5-4b4f-bc00-91acb2371dc0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*LPD3DHAL_DP2SETTRANSFORM, D3DHAL_DP2SETTRANSFORM, D3DHAL_DP2SETTRANSFORM structure [Display Devices], LPD3DHAL_DP2SETTRANSFORM, LPD3DHAL_DP2SETTRANSFORM structure pointer [Display Devices], _D3DHAL_DP2SETTRANSFORM, d3dhal/D3DHAL_DP2SETTRANSFORM, d3dhal/LPD3DHAL_DP2SETTRANSFORM, d3dstrct_0392a6fc-4098-4c82-92fa-5684be9fa195.xml, display.d3dhal_dp2settransform"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	d3dhal.h
api_name:
-	D3DHAL_DP2SETTRANSFORM
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2SETTRANSFORM
---

# _D3DHAL_DP2SETTRANSFORM structure
D3DHAL_DP2SETTRANSFORM structure is used to specify the transform state and matrix for <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>.

## Syntax
```
typedef struct _D3DHAL_DP2SETTRANSFORM {
  D3DTRANSFORMSTATETYPE xfrmType;
  D3DMATRIX             matrix;
} D3DHAL_DP2SETTRANSFORM;
```

## Members


`xfrmType`

Specifies the type of transform being done.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DTRANSFORMSTATE_PROJECTION

</td>
<td>
Specifies a projection transformation.

</td>
</tr>
<tr>
<td>
D3DTRANSFORMSTATE_VIEW

</td>
<td>
Specifies a view transformation.

</td>
</tr>
<tr>
<td>
D3DTRANSFORMSTATE_WORLD

</td>
<td>
Specifies a world transformation.

</td>
</tr>
</table>

`matrix`

Specifies the matrix used to perform the transform.

## Remarks
This structure is used with hardware transform and lighting and is used by the Direct3D runtime to inform the driver about the various transformation matrices.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dhal.h (include D3dhal.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545664">D3DHAL_DP2MULTIPLYTRANSFORM</a>



<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>