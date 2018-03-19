---
UID: NC:d3dkmddi.DXGKDDI_SETPALETTE
title: DXGKDDI_SETPALETTE
author: windows-driver-content
description: The DxgkDdiSetPalette function programs the color registers for palettized 8 bits-per-pixel (bpp) modes.
old-location: display\dxgkddisetpalette.htm
old-project: display
ms.assetid: 3a46bf84-df62-4247-b842-d5b131c96428
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_SETPALETTE, DmFunctions_88e6fd1a-1c14-4a4e-8616-c508b07ed94e.xml, DxgkDdiSetPalette, DxgkDdiSetPalette callback function [Display Devices], d3dkmddi/DxgkDdiSetPalette, display.dxgkddisetpalette
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkDdiSetPalette
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_SETPALETTE callback function
The <i>DxgkDdiSetPalette</i> function programs the color registers for palettized 8 bits-per-pixel (bpp) modes.

## Syntax

```
DXGKDDI_SETPALETTE DxgkddiSetpalette;

NTSTATUS DxgkddiSetpalette(
  IN_CONST_HANDLE hAdapter,
  IN_CONST_PDXGKARG_SETPALETTE pSetPalette
)
{...}
```

## Parameters

`hAdapter`

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.

`pSetPalette`

[in] A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_dxgkarg_setpalette.md">DXGKARG_SETPALETTE</a> structure that describes the palette to set for the display.


## Return Value

<i>DxgkDdiSetPalette</i> returns STATUS_SUCCESS, or an appropriate error result if the display palette is not successfully set.

## Remarks

Implementation of the <i>DxgkDdiSetPalette</i> function in the Windows Vista display driver model replaces <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_set_color_registers.md">IOCTL_VIDEO_SET_COLOR_REGISTERS</a> functionality in the Windows 2000 display driver model.

<i>DxgkDdiSetPalette</i> should be made pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkarg_setpalette.md">DXGKARG_SETPALETTE</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_palettedata.md">D3DKMDT_PALETTEDATA</a>