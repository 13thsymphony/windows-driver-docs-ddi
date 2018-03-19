---
UID: NE:d3d10umddi.D3D10_DDI_BLEND_OP
title: D3D10_DDI_BLEND_OP
author: windows-driver-content
description: The D3D10_DDI_BLEND_OP enumeration type contains values that identify blending operations in a call to the driver's CreateBlendState function.
old-location: display\d3d10_ddi_blend_op.htm
old-project: display
ms.assetid: 3743db2a-d613-4efb-ae73-80eb1bfd9410
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D10_DDI_BLEND_OP, D3D10_DDI_BLEND_OP enumeration [Display Devices], D3D10_DDI_BLEND_OP_ADD, D3D10_DDI_BLEND_OP_MAX, D3D10_DDI_BLEND_OP_MIN, D3D10_DDI_BLEND_OP_REV_SUBTRACT, D3D10_DDI_BLEND_OP_SUBTRACT, UMDisplayDriver_Dx10param_Structs_900c6f2c-fc2a-4982-a91e-b1ea29c5f0e4.xml, d3d10umddi/D3D10_DDI_BLEND_OP, d3d10umddi/D3D10_DDI_BLEND_OP_ADD, d3d10umddi/D3D10_DDI_BLEND_OP_MAX, d3d10umddi/D3D10_DDI_BLEND_OP_MIN, d3d10umddi/D3D10_DDI_BLEND_OP_REV_SUBTRACT, d3d10umddi/D3D10_DDI_BLEND_OP_SUBTRACT, display.d3d10_ddi_blend_op
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
-	D3D10_DDI_BLEND_OP
product: Windows
targetos: Windows
req.typenames: D3D10_DDI_BLEND_OP
---

# D3D10_DDI_BLEND_OP Enumeration
The D3D10_DDI_BLEND_OP enumeration type contains values that identify blending operations in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createblendstate.md">CreateBlendState</a> function.

## Syntax
````
typedef enum D3D10_DDI_BLEND_OP { 
  D3D10_DDI_BLEND_OP_ADD           = 1,
  D3D10_DDI_BLEND_OP_SUBTRACT      = 2,
  D3D10_DDI_BLEND_OP_REV_SUBTRACT  = 3,
  D3D10_DDI_BLEND_OP_MIN           = 4,
  D3D10_DDI_BLEND_OP_MAX           = 5
} D3D10_DDI_BLEND_OP;
````

## Constants

<table>
            
                <tr>
                    <td>D3D10_DDI_BLEND_OP_ADD</td>
                    <td>The result is the destination added to the source (Result = Source + Destination).</td>
                </tr>
            
                <tr>
                    <td>D3D10_DDI_BLEND_OP_SUBTRACT</td>
                    <td>The result is the destination subtracted from to the source (Result = Source - Destination).</td>
                </tr>
            
                <tr>
                    <td>D3D10_DDI_BLEND_OP_REV_SUBTRACT</td>
                    <td>The result is the source subtracted from the destination (Result = Destination - Source).</td>
                </tr>
            
                <tr>
                    <td>D3D10_DDI_BLEND_OP_MIN</td>
                    <td>The result is the minimum of the source and destination (Result = MIN(Source, Destination))</td>
                </tr>
            
                <tr>
                    <td>D3D10_DDI_BLEND_OP_MAX</td>
                    <td>The result is the maximum of the source and destination (Result = MAX(Source, Destination))</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createblendstate.md">CreateBlendState</a>