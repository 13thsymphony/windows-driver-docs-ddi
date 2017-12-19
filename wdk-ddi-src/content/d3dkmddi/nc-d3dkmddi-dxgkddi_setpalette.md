---
UID: NC.d3dkmddi.DXGKDDI_SETPALETTE
title: DXGKDDI_SETPALETTE
author: windows-driver-content
description: The DxgkDdiSetPalette function programs the color registers for palettized 8 bits-per-pixel (bpp) modes.
old-location: display\dxgkddisetpalette.htm
old-project: display
ms.assetid: 3a46bf84-df62-4247-b842-d5b131c96428
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
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
req.alt-api: DxgkDdiSetPalette
req.alt-loc: d3dkmddi.h
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
---

# DXGKDDI_SETPALETTE callback



## -description
The <i>DxgkDdiSetPalette</i> function programs the color registers for palettized 8 bits-per-pixel (bpp) modes.



## -prototype

````
DXGKDDI_SETPALETTE DxgkDdiSetPalette;

NTSTATUS APIENTRY DxgkDdiSetPalette(
  _In_ const HANDLE             hAdapter,
  _In_ const DXGKARG_SETPALETTE *pSetPalette
)
{ ... }
````


## -parameters

### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pSetPalette [in]

[in] A pointer to a <a href="display.dxgkarg_setpalette">DXGKARG_SETPALETTE</a> structure that describes the palette to set for the display. 


## -returns
<i>DxgkDdiSetPalette</i> returns STATUS_SUCCESS, or an appropriate error result if the display palette is not successfully set. 


## -remarks
Implementation of the <i>DxgkDdiSetPalette</i> function in the Windows Vista display driver model replaces <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_set_color_registers.md">IOCTL_VIDEO_SET_COLOR_REGISTERS</a> functionality in the Windows 2000 display driver model.

<i>DxgkDdiSetPalette</i> should be made pageable.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dkmdt_palettedata">D3DKMDT_PALETTEDATA</a>
</dt>
<dt>
<a href="display.dxgkarg_setpalette">DXGKARG_SETPALETTE</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_SETPALETTE callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

