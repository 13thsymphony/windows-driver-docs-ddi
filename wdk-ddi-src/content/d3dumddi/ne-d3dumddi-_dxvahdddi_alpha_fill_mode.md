---
UID: NE:d3dumddi._DXVAHDDDI_ALPHA_FILL_MODE
title: "_DXVAHDDDI_ALPHA_FILL_MODE"
author: windows-driver-content
description: The DXVAHDDDI_ALPHA_FILL_MODE enumeration contains values that identify the type of alpha fill mode to set.
old-location: display\dxvahdddi_alpha_fill_mode.htm
old-project: display
ms.assetid: 6b0fdae8-d313-4281-bab0-b3dcc38b19e5
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DXVAHDDDI_ALPHA_FILL_MODE_BACKGROUND, d3dumddi/DXVAHDDDI_ALPHA_FILL_MODE_DESTINATION, d3dumddi/DXVAHDDDI_ALPHA_FILL_MODE_BACKGROUND, DXVAHDDDI_ALPHA_FILL_MODE_SOURCE_STREAM, d3dumddi/DXVAHDDDI_ALPHA_FILL_MODE_SOURCE_STREAM, DXVA2_Structs_bc53b063-f00e-4589-8bf7-d397925dda55.xml, DXVAHDDDI_ALPHA_FILL_MODE_DESTINATION, DXVAHDDDI_ALPHA_FILL_MODE, DXVAHDDDI_ALPHA_FILL_MODE_OPAQUE, d3dumddi/DXVAHDDDI_ALPHA_FILL_MODE, d3dumddi/DXVAHDDDI_ALPHA_FILL_MODE_OPAQUE, _DXVAHDDDI_ALPHA_FILL_MODE, display.dxvahdddi_alpha_fill_mode, DXVAHDDDI_ALPHA_FILL_MODE enumeration [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_ALPHA_FILL_MODE is supported beginning with the Windows 7 operating system.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	DXVAHDDDI_ALPHA_FILL_MODE
product: Windows
targetos: Windows
req.typenames: DXVAHDDDI_ALPHA_FILL_MODE
---

# _DXVAHDDDI_ALPHA_FILL_MODE Enumeration
The DXVAHDDDI_ALPHA_FILL_MODE enumeration contains values that identify the type of alpha fill mode to set.

## Syntax
````
typedef enum _DXVAHDDDI_ALPHA_FILL_MODE { 
  DXVAHDDDI_ALPHA_FILL_MODE_OPAQUE         = 0,
  DXVAHDDDI_ALPHA_FILL_MODE_BACKGROUND     = 1,
  DXVAHDDDI_ALPHA_FILL_MODE_DESTINATION    = 2,
  DXVAHDDDI_ALPHA_FILL_MODE_SOURCE_STREAM  = 3
} DXVAHDDDI_ALPHA_FILL_MODE;
````

## Constants

<table>
            
                <tr>
                    <td>DXVAHDDDI_ALPHA_FILL_MODE_BACKGROUND</td>
                    <td>A value that specifies to fill the output with the alpha channel data of the background. For more information about background color, see <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_blt_state_background_color_data.md">DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA</a>.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_ALPHA_FILL_MODE_DESTINATION</td>
                    <td>A value that specifies to keep the alpha channel data unchanged on the target output.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_ALPHA_FILL_MODE_OPAQUE</td>
                    <td>A value that specifies to fill the output with opaque alpha channel data.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_ALPHA_FILL_MODE_SOURCE_STREAM</td>
                    <td>A value that specifies to fill the output with the alpha channel data of the destination rectangle in which the source rectangle of the specified input stream is scaled. For more information about the conditions for this value, see the Remarks section of <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_blt_state_alpha_fill_data.md">DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA</a>.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | DXVAHDDDI_ALPHA_FILL_MODE is supported beginning with the Windows 7 operating system. DXVAHDDDI_ALPHA_FILL_MODE is supported beginning with the Windows 7 operating system. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_blt_state_background_color_data.md">DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA</a>



<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_blt_state_alpha_fill_data.md">DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_ALPHA_FILL_MODE enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>