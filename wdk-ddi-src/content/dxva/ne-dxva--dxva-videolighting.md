---
UID: NE.dxva._DXVA_VideoLighting
title: DXVA_VideoLighting
author: windows-driver-content
description: The DXVA_VideoLighting enumeration type contains enumerators that identify lighting conditions for viewing video.
old-location: display\dxva_videolighting.htm
old-project: display
ms.assetid: 09adfa3f-443b-4500-bb08-27f91da20778
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGI_GAMMA_CONTROL_CAPABILITIES, DXGI_GAMMA_CONTROL_CAPABILITIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: This enumeration type applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVA_VideoLighting
req.alt-loc: dxva.h
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
req.iface: 
---

# DXVA_VideoLighting enumeration



## -description
<p>The DXVA_VideoLighting enumeration type contains enumerators that identify lighting conditions for viewing video.</p>


## -syntax

````
typedef enum _DXVA_VideoLighting { 
  DXVA_VideoLightingShift     = (DXVA_ExtColorData_ShiftBase + 10),
  DXVA_VideoLightingMask      = DXVAColorMask(4, DXVA_VideoLightingShift),
  DXVA_VideoLighting_Unknown  = 0,
  DXVA_VideoLighting_bright   = 1,
  DXVA_VideoLighting_office   = 2,
  DXVA_VideoLighting_dim      = 3,
  DXVA_VideoLighting_dark     = 4
} DXVA_VideoLighting;
````


## -enum-fields
<dl>

### -field <a id="DXVA_VideoLightingShift"></a><a id="dxva_videolightingshift"></a><a id="DXVA_VIDEOLIGHTINGSHIFT"></a><b>DXVA_VideoLightingShift</b>

<dd>
<p>Specifies to shift bits by 18 positions (DXVA_ExtColorData_ShiftBase + 10, or 8 + 10).</p>
</dd>

### -field <a id="DXVA_VideoLightingMask"></a><a id="dxva_videolightingmask"></a><a id="DXVA_VIDEOLIGHTINGMASK"></a><b>DXVA_VideoLightingMask</b>

<dd>
<p>Specifies the video lighting mask. 4 (0x003C0000) bits of a DWORD can be used to specify video lighting.</p>
</dd>

### -field <a id="DXVA_VideoLighting_Unknown"></a><a id="dxva_videolighting_unknown"></a><a id="DXVA_VIDEOLIGHTING_UNKNOWN"></a><b>DXVA_VideoLighting_Unknown</b>

<dd>
<p>Specifies that the video lighting condition is not specified. The default is dim.</p>
</dd>

### -field <a id="DXVA_VideoLighting_bright"></a><a id="dxva_videolighting_bright"></a><a id="DXVA_VIDEOLIGHTING_BRIGHT"></a><b>DXVA_VideoLighting_bright</b>

<dd>
<p>Specifies bright light for viewing video (for example, outside lighting conditions).</p>
</dd>

### -field <a id="DXVA_VideoLighting_office"></a><a id="dxva_videolighting_office"></a><a id="DXVA_VIDEOLIGHTING_OFFICE"></a><b>DXVA_VideoLighting_office</b>

<dd>
<p>Specifies a medium brightness light for viewing video (for example, lighting conditions in home offices).</p>
</dd>

### -field <a id="DXVA_VideoLighting_dim"></a><a id="dxva_videolighting_dim"></a><a id="DXVA_VIDEOLIGHTING_DIM"></a><b>DXVA_VideoLighting_dim</b>

<dd>
<p>Specifies a dim light for viewing video (for example, low-level lighting in a living room while watching television). </p>
</dd>

### -field <a id="DXVA_VideoLighting_dark"></a><a id="dxva_videolighting_dark"></a><a id="DXVA_VIDEOLIGHTING_DARK"></a><b>DXVA_VideoLighting_dark</b>

<dd>
<p>Specifies near darkness for viewing video (for example, movie-theatre lighting).</p>
</dd>
</dl>

## -remarks
<p>One of the enumerators of DXVA_VideoLighting can be specified in the <b>VideoLighting</b> member of the <a href="..\dxva\ns-dxva--dxva-extendedformat.md">DXVA_ExtendedFormat</a> structure.</p>

<p>The video lighting enumerators can be used to alter the gamma to generate a comparable experience in a different lighting condition. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>This enumeration type applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dxva.h (include Dxva.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dxva\ns-dxva--dxva-extendedformat.md">DXVA_ExtendedFormat</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_VideoLighting enumeration%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
