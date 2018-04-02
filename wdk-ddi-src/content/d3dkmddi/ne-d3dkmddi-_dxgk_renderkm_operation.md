---
UID: NE:d3dkmddi._DXGK_RENDERKM_OPERATION
title: "_DXGK_RENDERKM_OPERATION"
author: windows-driver-content
description: The DXGK_RENDERKM_OPERATION enumeration indicates the type of GDI hardware-accelerated rendering operation to perform when the DxgkDdiRenderKm function is called.
old-location: display\dxgk_renderkm_operation.htm
old-project: display
ms.assetid: bde22894-97a1-42a8-97c1-ba9738c087b9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_GDIOP_ALPHABLEND, DXGK_GDIOP_BITBLT, DXGK_GDIOP_CLEARTYPEBLEND, DXGK_GDIOP_COLORFILL, DXGK_GDIOP_ESCAPE, DXGK_GDIOP_STRETCHBLT, DXGK_GDIOP_TRANSPARENTBLT, DXGK_RENDERKM_OPERATION, DXGK_RENDERKM_OPERATION enumeration [Display Devices], DmEnums_f7b836bc-00ed-4ecc-8bb7-460e3e44d165.xml, _DXGK_RENDERKM_OPERATION, d3dkmddi/DXGK_GDIOP_ALPHABLEND, d3dkmddi/DXGK_GDIOP_BITBLT, d3dkmddi/DXGK_GDIOP_CLEARTYPEBLEND, d3dkmddi/DXGK_GDIOP_COLORFILL, d3dkmddi/DXGK_GDIOP_ESCAPE, d3dkmddi/DXGK_GDIOP_STRETCHBLT, d3dkmddi/DXGK_GDIOP_TRANSPARENTBLT, d3dkmddi/DXGK_RENDERKM_OPERATION, display.dxgk_renderkm_operation
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
-	DXGK_RENDERKM_OPERATION
product: Windows
targetos: Windows
req.typenames: DXGK_RENDERKM_OPERATION
---

# _DXGK_RENDERKM_OPERATION Enumeration
The DXGK_RENDERKM_OPERATION enumeration indicates the type of GDI hardware-accelerated rendering operation to perform when the <a href="https://msdn.microsoft.com/5841934d-7e0a-4bb8-a7f8-17d8c0af351f">DxgkDdiRenderKm</a> function is called.

## Syntax
```
typedef enum _DXGK_RENDERKM_OPERATION {
  DXGK_GDIOP_BITBLT          ,
  DXGK_GDIOP_COLORFILL       ,
  DXGK_GDIOP_ALPHABLEND      ,
  DXGK_GDIOP_STRETCHBLT      ,
  DXGK_GDIOP_ESCAPE          ,
  DXGK_GDIOP_TRANSPARENTBLT  ,
  DXGK_GDIOP_CLEARTYPEBLEND
} DXGK_RENDERKM_OPERATION;
```

## Constants

<table>
            
                <tr>
                    <td>DXGK_GDIOP_BITBLT</td>
                    <td>Indicates a bit-block transfer (bitblt).</td>
                </tr>
            
                <tr>
                    <td>DXGK_GDIOP_COLORFILL</td>
                    <td>Indicates a color fill.</td>
                </tr>
            
                <tr>
                    <td>DXGK_GDIOP_ALPHABLEND</td>
                    <td>Indicates an alpha blend.</td>
                </tr>
            
                <tr>
                    <td>DXGK_GDIOP_STRETCHBLT</td>
                    <td>Indicates a stretch blt.</td>
                </tr>
            
                <tr>
                    <td>DXGK_GDIOP_ESCAPE</td>
                    <td>Reserved for future use. The driver should skip this command when setting the value of the <b>CommandSize</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562026">DXGK_RENDERKM_COMMAND</a> structure.</td>
                </tr>
            
                <tr>
                    <td>DXGK_GDIOP_TRANSPARENTBLT</td>
                    <td>Indicates a blt with transparency.</td>
                </tr>
            
                <tr>
                    <td>DXGK_GDIOP_CLEARTYPEBLEND</td>
                    <td>Indicates a ClearType blend.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of the Windows operating systems. Available in Windows 7 and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562026">DXGK_RENDERKM_COMMAND</a>



<a href="https://msdn.microsoft.com/5841934d-7e0a-4bb8-a7f8-17d8c0af351f">DxgkDdiRenderKm</a>