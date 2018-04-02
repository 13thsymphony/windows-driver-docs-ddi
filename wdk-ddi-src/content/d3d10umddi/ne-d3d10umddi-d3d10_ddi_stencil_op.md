---
UID: NE:d3d10umddi.D3D10_DDI_STENCIL_OP
title: D3D10_DDI_STENCIL_OP
author: windows-driver-content
description: The D3D10_DDI_STENCIL_OP enumeration type contains values that identify operations on stencil buffers in a call to the driver's CreateDepthStencilState function.
old-location: display\d3d10_ddi_stencil_op.htm
old-project: display
ms.assetid: 624decb3-6279-45ba-8cdd-5a52de80dd71
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D10_DDI_STENCIL_OP, D3D10_DDI_STENCIL_OP enumeration [Display Devices], D3D10_DDI_STENCIL_OP_DECR, D3D10_DDI_STENCIL_OP_DECR_SAT, D3D10_DDI_STENCIL_OP_INCR, D3D10_DDI_STENCIL_OP_INCR_SAT, D3D10_DDI_STENCIL_OP_INVERT, D3D10_DDI_STENCIL_OP_KEEP, D3D10_DDI_STENCIL_OP_REPLACE, D3D10_DDI_STENCIL_OP_ZERO, UMDisplayDriver_Dx10param_Structs_0d70cbc2-b62c-4dce-b1f4-65b4c99ed5d7.xml, d3d10umddi/D3D10_DDI_STENCIL_OP, d3d10umddi/D3D10_DDI_STENCIL_OP_DECR, d3d10umddi/D3D10_DDI_STENCIL_OP_DECR_SAT, d3d10umddi/D3D10_DDI_STENCIL_OP_INCR, d3d10umddi/D3D10_DDI_STENCIL_OP_INCR_SAT, d3d10umddi/D3D10_DDI_STENCIL_OP_INVERT, d3d10umddi/D3D10_DDI_STENCIL_OP_KEEP, d3d10umddi/D3D10_DDI_STENCIL_OP_REPLACE, d3d10umddi/D3D10_DDI_STENCIL_OP_ZERO, display.d3d10_ddi_stencil_op
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	D3D10_DDI_STENCIL_OP
product: Windows
targetos: Windows
req.typenames: D3D10_DDI_STENCIL_OP
---

# D3D10_DDI_STENCIL_OP Enumeration
The D3D10_DDI_STENCIL_OP enumeration type contains values that identify operations on stencil buffers in a call to the driver's <a href="https://msdn.microsoft.com/ed2da104-c4e8-43eb-80e0-10273b575020">CreateDepthStencilState</a> function.

## Syntax
```
typedef enum D3D10_DDI_STENCIL_OP {
  D3D10_DDI_STENCIL_OP_KEEP      ,
  D3D10_DDI_STENCIL_OP_ZERO      ,
  D3D10_DDI_STENCIL_OP_REPLACE   ,
  D3D10_DDI_STENCIL_OP_INCR_SAT  ,
  D3D10_DDI_STENCIL_OP_DECR_SAT  ,
  D3D10_DDI_STENCIL_OP_INVERT    ,
  D3D10_DDI_STENCIL_OP_INCR      ,
  D3D10_DDI_STENCIL_OP_DECR
} ;
```

## Constants

<table>
            
                <tr>
                    <td>D3D10_DDI_STENCIL_OP_KEEP</td>
                    <td>Do not update the entry in the stencil buffer. D3D10_DDI_STENCIL_OP_KEEP is the default value.</td>
                </tr>
            
                <tr>
                    <td>D3D10_DDI_STENCIL_OP_ZERO</td>
                    <td>Set the stencil-buffer entry to 0.</td>
                </tr>
            
                <tr>
                    <td>D3D10_DDI_STENCIL_OP_REPLACE</td>
                    <td>Replace the stencil-buffer entry with a reference value.</td>
                </tr>
            
                <tr>
                    <td>D3D10_DDI_STENCIL_OP_INCR_SAT</td>
                    <td>Increment the stencil-buffer entry, clamping to the maximum value.</td>
                </tr>
            
                <tr>
                    <td>D3D10_DDI_STENCIL_OP_DECR_SAT</td>
                    <td>Decrement the stencil-buffer entry, clamping to zero.</td>
                </tr>
            
                <tr>
                    <td>D3D10_DDI_STENCIL_OP_INVERT</td>
                    <td>Invert the bits in the stencil-buffer entry.</td>
                </tr>
            
                <tr>
                    <td>D3D10_DDI_STENCIL_OP_INCR</td>
                    <td>Increment the stencil-buffer entry, wrapping to zero if the new value exceeds the maximum value.</td>
                </tr>
            
                <tr>
                    <td>D3D10_DDI_STENCIL_OP_DECR</td>
                    <td>Decrement the stencil-buffer entry, wrapping to the maximum value if the new value is less than zero.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/ed2da104-c4e8-43eb-80e0-10273b575020">CreateDepthStencilState</a>