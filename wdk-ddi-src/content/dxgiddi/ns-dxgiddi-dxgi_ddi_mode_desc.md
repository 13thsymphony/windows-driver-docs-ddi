---
UID: NS.DXGIDDI.DXGI_DDI_MODE_DESC
title: DXGI_DDI_MODE_DESC
author: windows-driver-content
description: The DXGI_DDI_MODE_DESC structure describes a display mode.
old-location: display\dxgi_ddi_mode_desc.htm
old-project: display
ms.assetid: 9924f914-2812-4953-85d1-9c777404418b
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: DXGI_DDI_MODE_DESC, DXGI_DDI_MODE_DESC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGI_DDI_MODE_DESC
req.alt-loc: dxgiddi.h
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
---

# DXGI_DDI_MODE_DESC structure



## -description
The DXGI_DDI_MODE_DESC structure describes a display mode.



## -syntax

````
typedef struct DXGI_DDI_MODE_DESC {
  UINT                         Width;
  UINT                         Height;
  DXGI_FORMAT                  Format;
  DXGI_DDI_RATIONAL            RefreshRate;
  DXGI_DDI_MODE_SCANLINE_ORDER ScanlineOrdering;
  DXGI_DDI_MODE_ROTATION       Rotation;
  DXGI_DDI_MODE_SCALING        Scaling;
} DXGI_DDI_MODE_DESC;
````


## -struct-fields

### -field Width

[out] The screen width of the display mode, in pixels.


### -field Height

[out] The screen height of the display mode, in pixels.


### -field Format

[out] A DXGI_FORMAT-typed value that indicates the pixel format of the display mode.


### -field RefreshRate

[out] A <a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_rational.md">DXGI_DDI_RATIONAL</a> structure that indicates the refresh rate of the display mode.


### -field ScanlineOrdering

[out] A <a href="..\dxgiddi\ne-dxgiddi-dxgi_ddi_mode_scanline_order.md">DXGI_DDI_MODE_SCANLINE_ORDER</a>-typed value that indicates how scan lines are ordered in the display mode.


### -field Rotation

[out] A <a href="..\dxgiddi\ne-dxgiddi-dxgi_ddi_mode_rotation.md">DXGI_DDI_MODE_ROTATION</a>-typed value that identifies the orientation of the display mode.


### -field Scaling

[out] A <a href="..\dxgiddi\ne-dxgiddi-dxgi_ddi_mode_scaling.md">DXGI_DDI_MODE_SCALING</a>-typed value that identifies the scaling of the display mode.


## -remarks


## -requirements
<table>
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
<dt>Dxgiddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dxgiddi\ne-dxgiddi-dxgi_ddi_mode_rotation.md">DXGI_DDI_MODE_ROTATION</a>
</dt>
<dt>
<a href="..\dxgiddi\ne-dxgiddi-dxgi_ddi_mode_scaling.md">DXGI_DDI_MODE_SCALING</a>
</dt>
<dt>
<a href="..\dxgiddi\ne-dxgiddi-dxgi_ddi_mode_scanline_order.md">DXGI_DDI_MODE_SCANLINE_ORDER</a>
</dt>
<dt>
<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_primary_desc.md">DXGI_DDI_PRIMARY_DESC</a>
</dt>
<dt>
<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_rational.md">DXGI_DDI_RATIONAL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_MODE_DESC structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

