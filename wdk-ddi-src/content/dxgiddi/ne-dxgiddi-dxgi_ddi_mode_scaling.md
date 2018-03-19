---
UID: NE:dxgiddi.DXGI_DDI_MODE_SCALING
title: DXGI_DDI_MODE_SCALING
author: windows-driver-content
description: The DXGI_DDI_MODE_SCALING enumeration type contains values that identify the scaling support for a display.
old-location: display\dxgi_ddi_mode_scaling.htm
old-project: display
ms.assetid: dfe37343-18a6-46f2-b23f-52fc0ca2f800
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGI_DDI_MODE_SCALING, DXGI_DDI_MODE_SCALING enumeration [Display Devices], DXGI_DDI_MODE_SCALING_CENTERED, DXGI_DDI_MODE_SCALING_STRETCHED, DXGI_DDI_MODE_SCALING_UNSPECIFIED, UMDisplayDriver_Dx10param_Structs_fce25008-9fff-4a5a-9bdc-2e9a6055ef06.xml, display.dxgi_ddi_mode_scaling, dxgiddi/DXGI_DDI_MODE_SCALING, dxgiddi/DXGI_DDI_MODE_SCALING_CENTERED, dxgiddi/DXGI_DDI_MODE_SCALING_STRETCHED, dxgiddi/DXGI_DDI_MODE_SCALING_UNSPECIFIED
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dxgiddi.h
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
-	dxgiddi.h
api_name:
-	DXGI_DDI_MODE_SCALING
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_MODE_SCALING
---

# DXGI_DDI_MODE_SCALING Enumeration
The DXGI_DDI_MODE_SCALING enumeration type contains values that identify the scaling support for a display.

## Syntax
````
typedef enum DXGI_DDI_MODE_SCALING { 
  DXGI_DDI_MODE_SCALING_UNSPECIFIED  = 0,
  DXGI_DDI_MODE_SCALING_STRETCHED    = 1,
  DXGI_DDI_MODE_SCALING_CENTERED     = 2
} DXGI_DDI_MODE_SCALING;
````

## Constants

<table>
            
                <tr>
                    <td>DXGI_DDI_MODE_SCALING_UNSPECIFIED</td>
                    <td>A DXGI_DDI_MODE_SCALING-typed variable has not yet been assigned a meaningful value.</td>
                </tr>
            
                <tr>
                    <td>DXGI_DDI_MODE_SCALING_STRETCHED</td>
                    <td>Stretched content can be displayed.</td>
                </tr>
            
                <tr>
                    <td>DXGI_DDI_MODE_SCALING_CENTERED</td>
                    <td>Centered content can be displayed.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | dxgiddi.h (include D3d10umddi.h) |

## See Also

<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_mode_desc.md">DXGI_DDI_MODE_DESC</a>