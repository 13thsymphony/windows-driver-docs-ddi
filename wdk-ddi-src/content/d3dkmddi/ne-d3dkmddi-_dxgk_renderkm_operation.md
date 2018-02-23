---
UID: NE:d3dkmddi._DXGK_RENDERKM_OPERATION
title: "_DXGK_RENDERKM_OPERATION"
author: windows-driver-content
description: The DXGK_RENDERKM_OPERATION enumeration indicates the type of GDI hardware-accelerated rendering operation to perform when the DxgkDdiRenderKm function is called.
old-location: display\dxgk_renderkm_operation.htm
old-project: display
ms.assetid: bde22894-97a1-42a8-97c1-ba9738c087b9
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: d3dkmddi/DXGK_GDIOP_ALPHABLEND, DXGK_GDIOP_COLORFILL, _DXGK_RENDERKM_OPERATION, d3dkmddi/DXGK_GDIOP_COLORFILL, d3dkmddi/DXGK_GDIOP_TRANSPARENTBLT, DXGK_GDIOP_TRANSPARENTBLT, DmEnums_f7b836bc-00ed-4ecc-8bb7-460e3e44d165.xml, d3dkmddi/DXGK_GDIOP_ESCAPE, DXGK_RENDERKM_OPERATION, d3dkmddi/DXGK_GDIOP_BITBLT, DXGK_GDIOP_CLEARTYPEBLEND, d3dkmddi/DXGK_GDIOP_STRETCHBLT, DXGK_GDIOP_STRETCHBLT, d3dkmddi/DXGK_GDIOP_CLEARTYPEBLEND, DXGK_GDIOP_BITBLT, DXGK_RENDERKM_OPERATION enumeration [Display Devices], DXGK_GDIOP_ESCAPE, display.dxgk_renderkm_operation, d3dkmddi/DXGK_RENDERKM_OPERATION, DXGK_GDIOP_ALPHABLEND
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_RENDERKM_OPERATION
product: Windows
targetos: Windows
req.typenames: DXGK_RENDERKM_OPERATION
---

# _DXGK_RENDERKM_OPERATION Enumeration
The DXGK_RENDERKM_OPERATION enumeration indicates the type of GDI hardware-accelerated rendering operation to perform when the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_renderkm.md">DxgkDdiRenderKm</a> function is called.

## Syntax
````
typedef enum _DXGK_RENDERKM_OPERATION { 
  DXGK_GDIOP_BITBLT          = 1,
  DXGK_GDIOP_COLORFILL       = 2,
  DXGK_GDIOP_ALPHABLEND      = 3,
  DXGK_GDIOP_STRETCHBLT      = 4,
  DXGK_GDIOP_ESCAPE          = 5,
  DXGK_GDIOP_TRANSPARENTBLT  = 6,
  DXGK_GDIOP_CLEARTYPEBLEND  = 7
} DXGK_RENDERKM_OPERATION;
````

## Constants

<table>
            
                <tr>
                    <td>DXGK_GDIOP_ALPHABLEND</td>
                    <td>Indicates an alpha blend.</td>
                </tr>
            
                <tr>
                    <td>DXGK_GDIOP_BITBLT</td>
                    <td>Indicates a bit-block transfer (bitblt).</td>
                </tr>
            
                <tr>
                    <td>DXGK_GDIOP_CLEARTYPEBLEND</td>
                    <td>Indicates a ClearType blend.</td>
                </tr>
            
                <tr>
                    <td>DXGK_GDIOP_COLORFILL</td>
                    <td>Indicates a color fill.</td>
                </tr>
            
                <tr>
                    <td>DXGK_GDIOP_ESCAPE</td>
                    <td>Reserved for future use. The driver should skip this command when setting the value of the <b>CommandSize</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_renderkm_command.md">DXGK_RENDERKM_COMMAND</a> structure.</td>
                </tr>
            
                <tr>
                    <td>DXGK_GDIOP_STRETCHBLT</td>
                    <td>Indicates a stretch blt.</td>
                </tr>
            
                <tr>
                    <td>DXGK_GDIOP_TRANSPARENTBLT</td>
                    <td>Indicates a blt with transparency.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of the Windows operating systems. Available in Windows 7 and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_renderkm.md">DxgkDdiRenderKm</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_renderkm_command.md">DXGK_RENDERKM_COMMAND</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_RENDERKM_OPERATION enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>