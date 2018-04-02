---
UID: NE:dxgiddi.DXGI_DDI_MODE_SCANLINE_ORDER
title: DXGI_DDI_MODE_SCANLINE_ORDER
author: windows-driver-content
description: The DXGI_DDI_MODE_SCANLINE_ORDER enumeration type contains values that identify how scan lines are ordered in a display mode.
old-location: display\dxgi_ddi_mode_scanline_order.htm
old-project: display
ms.assetid: 114a6f0d-22ec-4306-81b4-56cf882f167f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGI_DDI_MODE_SCANLINE_ORDER, DXGI_DDI_MODE_SCANLINE_ORDER enumeration [Display Devices], DXGI_DDI_MODE_SCANLINE_ORDER_LOWER_FIELD_FIRST, DXGI_DDI_MODE_SCANLINE_ORDER_PROGRESSIVE, DXGI_DDI_MODE_SCANLINE_ORDER_UNSPECIFIED, DXGI_DDI_MODE_SCANLINE_ORDER_UPPER_FIELD_FIRST, UMDisplayDriver_Dx10param_Structs_fe7ff8f4-48e3-4ec5-a401-35d729a17440.xml, display.dxgi_ddi_mode_scanline_order, dxgiddi/DXGI_DDI_MODE_SCANLINE_ORDER, dxgiddi/DXGI_DDI_MODE_SCANLINE_ORDER_LOWER_FIELD_FIRST, dxgiddi/DXGI_DDI_MODE_SCANLINE_ORDER_PROGRESSIVE, dxgiddi/DXGI_DDI_MODE_SCANLINE_ORDER_UNSPECIFIED, dxgiddi/DXGI_DDI_MODE_SCANLINE_ORDER_UPPER_FIELD_FIRST
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
-	DXGI_DDI_MODE_SCANLINE_ORDER
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_MODE_SCANLINE_ORDER
---

# DXGI_DDI_MODE_SCANLINE_ORDER Enumeration
The DXGI_DDI_MODE_SCANLINE_ORDER enumeration type contains values that identify how scan lines are ordered in a display mode.

## Syntax
```
typedef enum DXGI_DDI_MODE_SCANLINE_ORDER {
  DXGI_DDI_MODE_SCANLINE_ORDER_UNSPECIFIED        ,
  DXGI_DDI_MODE_SCANLINE_ORDER_PROGRESSIVE        ,
  DXGI_DDI_MODE_SCANLINE_ORDER_UPPER_FIELD_FIRST  ,
  DXGI_DDI_MODE_SCANLINE_ORDER_LOWER_FIELD_FIRST
} ;
```

## Constants

<table>
            
                <tr>
                    <td>DXGI_DDI_MODE_SCANLINE_ORDER_UNSPECIFIED</td>
                    <td>A DXGI_DDI_MODE_SCANLINE_ORDER-typed variable has not yet been assigned a meaningful value.</td>
                </tr>
            
                <tr>
                    <td>DXGI_DDI_MODE_SCANLINE_ORDER_PROGRESSIVE</td>
                    <td>Each field contains an entire frame.</td>
                </tr>
            
                <tr>
                    <td>DXGI_DDI_MODE_SCANLINE_ORDER_UPPER_FIELD_FIRST</td>
                    <td>Each field contains half of a frame, and the odd scan lines are displayed first.</td>
                </tr>
            
                <tr>
                    <td>DXGI_DDI_MODE_SCANLINE_ORDER_LOWER_FIELD_FIRST</td>
                    <td>Each field contains half of a frame, and the even scan lines are displayed first.</td>
                </tr>
</table>

## Remarks

The values of the DXGI_DDI_MODE_SCANLINE_ORDER enumeration type indicate whether the image that is displayed on the monitor contains the entire content of a video frame or only half of the content (that is, either the even or odd scan lines, which occur interchangeably). The values also indicate which field comes first in the order.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | dxgiddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557499">DXGI_DDI_MODE_DESC</a>