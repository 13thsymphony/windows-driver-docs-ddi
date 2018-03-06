---
UID: NE:d3dkmddi._DXGK_GDIROP_BITBLT
title: "_DXGK_GDIROP_BITBLT"
author: windows-driver-content
description: The DXGK_GDIROP_COLORFILL enumeration indicates the type of GDI raster operation (ROP) to implement in a GDI hardware-accelerated bit-block transfer (bitblt) operation.
old-location: display\dxgk_gdirop_bitblt.htm
old-project: display
ms.assetid: f5f337dd-ab7a-4a9f-af3c-2d29dbdffe7b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_GDIROP_BITBLT, DXGK_GDIROP_BITBLT enumeration [Display Devices], DXGK_GDIROP_INVALID, DXGK_GDIROP_ROP3, DXGK_GDIROP_SRCAND, DXGK_GDIROP_SRCCOPY, DXGK_GDIROP_SRCINVERT, DXGK_GDIROP_SRCOR, DmEnums_ac0fe82c-71cb-4756-a580-37d138873b2d.xml, _DXGK_GDIROP_BITBLT, d3dkmddi/DXGK_GDIROP_BITBLT, d3dkmddi/DXGK_GDIROP_INVALID, d3dkmddi/DXGK_GDIROP_ROP3, d3dkmddi/DXGK_GDIROP_SRCAND, d3dkmddi/DXGK_GDIROP_SRCCOPY, d3dkmddi/DXGK_GDIROP_SRCINVERT, d3dkmddi/DXGK_GDIROP_SRCOR, display.dxgk_gdirop_bitblt
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_GDIROP_BITBLT
product: Windows
targetos: Windows
req.typenames: DXGK_GDIROP_BITBLT
---

# _DXGK_GDIROP_BITBLT Enumeration
The DXGK_GDIROP_COLORFILL enumeration indicates the type of GDI raster operation (ROP) to implement in a GDI hardware-accelerated bit-block transfer (bitblt) operation.

## Syntax
````
typedef enum _DXGK_GDIROP_BITBLT { 
  DXGK_GDIROP_INVALID    = 0,
  DXGK_GDIROP_SRCCOPY    = 1,
  DXGK_GDIROP_SRCINVERT  = 2,
  DXGK_GDIROP_SRCAND     = 3,
  DXGK_GDIROP_SRCOR      = 4,
  DXGK_GDIROP_ROP3       = 5
} DXGK_GDIROP_BITBLT;
````

## Constants

<table>
            
                <tr>
                    <td>DXGK_GDIROP_INVALID</td>
                    <td>Indicates that the GDI raster operation is invalid.</td>
                </tr>
            
                <tr>
                    <td>DXGK_GDIROP_ROP3</td>
                    <td>Indicates that a ternary GDI raster operation (ROP3) will be applied.</td>
                </tr>
            
                <tr>
                    <td>DXGK_GDIROP_SRCAND</td>
                    <td>Indicates that the color of each pixel of the source rectangle is combined with the color of the respective pixel of the destination rectangle by using the Boolean <b>AND</b> operator.</td>
                </tr>
            
                <tr>
                    <td>DXGK_GDIROP_SRCCOPY</td>
                    <td>Indicates that the source rectangle is copied to the destination rectangle.</td>
                </tr>
            
                <tr>
                    <td>DXGK_GDIROP_SRCINVERT</td>
                    <td>Indicates that the color of each pixel of the source rectangle is combined with the color of the respective pixel of the destination rectangle by using the Boolean <b>XOR</b> operator.</td>
                </tr>
            
                <tr>
                    <td>DXGK_GDIROP_SRCOR</td>
                    <td>Indicates that the color of each pixel of the source rectangle is combined with the color of the respective pixel of the destination rectangle by using the Boolean <b>OR</b> operator.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of the Windows operating systems. Available in Windows 7 and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |