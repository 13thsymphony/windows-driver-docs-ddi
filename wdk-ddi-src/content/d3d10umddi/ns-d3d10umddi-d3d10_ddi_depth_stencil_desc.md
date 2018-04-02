---
UID: NS:d3d10umddi.D3D10_DDI_DEPTH_STENCIL_DESC
title: D3D10_DDI_DEPTH_STENCIL_DESC
author: windows-driver-content
description: The D3D10_DDI_DEPTH_STENCIL_DESC structure describes a depth stencil state.
old-location: display\d3d10_ddi_depth_stencil_desc.htm
old-project: display
ms.assetid: d1043d5b-6f2c-4c2f-894a-ae6870865257
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D10_DDI_DEPTH_STENCIL_DESC, D3D10_DDI_DEPTH_STENCIL_DESC structure [Display Devices], UMDisplayDriver_Dx10param_Structs_4e9cbeba-8eb3-43ea-891a-1b57c82cd3ef.xml, d3d10umddi/D3D10_DDI_DEPTH_STENCIL_DESC, display.d3d10_ddi_depth_stencil_desc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
-	d3d10umddi.h
api_name:
-	D3D10_DDI_DEPTH_STENCIL_DESC
product:
- Windows
targetos: Windows
req.typenames: D3D10_DDI_DEPTH_STENCIL_DESC
---

# D3D10_DDI_DEPTH_STENCIL_DESC structure
The D3D10_DDI_DEPTH_STENCIL_DESC structure describes a depth stencil state.

## Syntax
```
typedef struct D3D10_DDI_DEPTH_STENCIL_DESC {
  BOOL                           DepthEnable;
  D3D10_DDI_DEPTH_WRITE_MASK     DepthWriteMask;
  D3D10_DDI_COMPARISON_FUNC      DepthFunc;
  BOOL                           StencilEnable;
  BOOL                           FrontEnable;
  BOOL                           BackEnable;
  UINT8                          StencilReadMask;
  UINT8                          StencilWriteMask;
  D3D10_DDI_DEPTH_STENCILOP_DESC FrontFace;
  D3D10_DDI_DEPTH_STENCILOP_DESC BackFace;
};
```

## Members


`DepthEnable`

[in] A Boolean value that specifies whether depth is enabled. <b>TRUE</b> indicates depth is enabled; <b>FALSE</b> indicates depth is disabled.

`DepthWriteMask`

[in] A bitwise value that indicates the write properties for a depth stencil state. This member is a valid bitwise OR of the following values from the D3D10_DDI_DEPTH_WRITE_MASK enumeration.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3D10_DDI_DEPTH_WRITE_MASK_ZERO (0)

</td>
<td>
No properties

</td>
</tr>
<tr>
<td>
D3D10_DDI_DEPTH_WRITE_MASK_ALL (1)

</td>
<td>
All properties

</td>
</tr>
</table>

`DepthFunc`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff541933">D3D10_DDI_COMPARISON_FUNC</a>-typed value that indicates the depth-comparison function to perform.

`StencilEnable`

[in] A Boolean value that specifies whether stencil is enabled. <b>TRUE</b> indicates stencil is enabled; <b>FALSE</b> indicates stencil is disabled.

`FrontEnable`

[in] A Boolean value that specifies whether the performance of stencil operations on forward-facing polygons is enabled. <b>TRUE</b> indicates that the performance on forward-facing polygons is enabled; <b>FALSE</b> indicates that it is disabled.

`BackEnable`

[in] A Boolean value that specifies whether the performance of stencil operations on back-facing polygons is enabled. <b>TRUE</b> indicates that the performance on back-facing polygons is enabled; <b>FALSE</b> indicates that it is disabled.

`StencilReadMask`

[in] An 8-bit bitwise value that the driver uses in a bitwise AND operation with the stencil value in the stencil buffer immediately after reading the stencil value out of the stencil buffer.

`StencilWriteMask`

[in] An 8-bit bitwise value that the driver uses in a bitwise AND operation with the current stencil value before writing the result back out to the stencil buffer.

`FrontFace`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff541938">D3D10_DDI_DEPTH_STENCILOP_DESC</a> structure that describes the stencil operation to perform on forward-facing polygons.

`BackFace`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff541938">D3D10_DDI_DEPTH_STENCILOP_DESC</a> structure that describes the stencil operation to perform on back-facing polygons.

## Remarks
If the <b>StencilEnable</b> member is set to <b>TRUE</b>, the <b>FrontEnable</b> member, <b>BackEnable</b> member, or both must also be set to <b>TRUE</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/dcc02e1e-97e0-4ccd-8329-8219cad5d09a">CalcPrivateDepthStencilStateSize</a>



<a href="https://msdn.microsoft.com/ed2da104-c4e8-43eb-80e0-10273b575020">CreateDepthStencilState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541933">D3D10_DDI_COMPARISON_FUNC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541938">D3D10_DDI_DEPTH_STENCILOP_DESC</a>