---
UID: NS.d3dumddi._D3DDDI_LIGHT
title: D3DDDI_LIGHT
author: windows-driver-content
description: The D3DDDI_LIGHT structure describes a set of lighting properties.
old-location: display\d3dddi_light.htm
old-project: display
ms.assetid: 53204334-bf91-46ad-93cc-84a4ec17ae54
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DDDI_LIGHT, D3DDDI_LIGHT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_LIGHT
req.alt-loc: d3dumddi.h
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

# D3DDDI_LIGHT structure



## -description
<p>The D3DDDI_LIGHT structure describes a set of lighting properties. </p>


## -syntax

````
typedef struct _D3DDDI_LIGHT {
  D3DLIGHTTYPE  Type;
  D3DCOLORVALUE Diffuse;
  D3DCOLORVALUE Specular;
  D3DCOLORVALUE Ambient;
  D3DVECTOR     Position;
  D3DVECTOR     Direction;
  FLOAT         Range;
  FLOAT         Falloff;
  FLOAT         Attenuation0;
  FLOAT         Attenuation1;
  FLOAT         Attenuation2;
  FLOAT         Theta;
  FLOAT         Phi;
} D3DDDI_LIGHT;
````


## -struct-fields
<dl>

### -field Type

<dd>
<p>[in] A D3DLIGHTTYPE-typed value that indicates the type of the light source. For more information about D3DLIGHTTYPE, see the Microsoft Windows SDK documentation.</p>
</dd>

### -field Diffuse

<dd>
<p>[in] A D3DCOLORVALUE structure that indicates the diffuse color that is emitted by the light. For more information about D3DCOLORVALUE, see the Windows SDK documentation.</p>
</dd>

### -field Specular

<dd>
<p>[in] A D3DCOLORVALUE structure that indicates the specular color that is emitted by the light.</p>
</dd>

### -field Ambient

<dd>
<p>[in] A D3DCOLORVALUE structure that indicates the ambient color that is emitted by the light.</p>
</dd>

### -field Position

<dd>
<p>[in] A D3DVECTOR structure that indicates the position of the light in world space. This member has no meaning for directional lights (that is, if D3DLIGHT_DIRECTIONAL is set in the <b>Type</b> member) and is ignored in that situation. For more information about D3DVECTOR, see the Windows SDK documentation.</p>
</dd>

### -field Direction

<dd>
<p>[in] A D3DVECTOR structure that indicates the direction that the light is pointing in world space. This member has meaning only for directional lights and spotlights (that is, if D3DLIGHT_DIRECTIONAL and D3DLIGHT_SPOT are set in <b>Type</b>). This vector is not required to be normalized, but it should have a nonzero length.</p>
</dd>

### -field Range

<dd>
<p>[in] The distance beyond which the light has no effect. The maximum allowable value for this member is D3DLIGHT_RANGE_MAX, which is defined as the square root of FLT_MAX. This member does not affect directional lights.</p>
</dd>

### -field Falloff

<dd>
<p>[in] The decrease in illumination between a spotlight's inner cone (the angle that is specified by the <b>Theta</b> member) and the outer edge of the outer cone (the angle that is specified by the <b>Phi</b> member). The effect of falloff on the lighting is subtle. Furthermore, a small performance penalty is incurred by shaping the falloff curve. For these reasons, most developers set this member to 1.0.</p>
</dd>

### -field Attenuation0

<dd>
<p>[in] The light's constant attenuation factor. Attenuation values specify how the light intensity changes over distance. Attenuation does not affect directional lights. Valid values for this member range from 0.0 through infinity.</p>
</dd>

### -field Attenuation1

<dd>
<p>[in] The light's linear attenuation factor. Attenuation values specify how the light intensity changes over distance. Attenuation does not affect directional lights. Valid values for this member range from 0.0 through infinity.</p>
</dd>

### -field Attenuation2

<dd>
<p>[in] The light's quadratic attenuation factor. Attenuation values specify how the light intensity changes over distance. Attenuation does not affect directional lights. Valid values for this member range from 0.0 through infinity.</p>
</dd>

### -field Theta

<dd>
<p>[in] The angle, in radians, of a spotlight's inner cone--that is, the fully illuminated spotlight cone. This value must be in the range from 0 through the value that is specified by the <b>Phi</b> member.</p>
</dd>

### -field Phi

<dd>
<p>[in] The angle, in radians, that defines the outer edge of the spotlight's outer cone. Points outside this cone are not lit by the spotlight. This value must be between 0 and Pi.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-setlight.md">SetLight</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_LIGHT structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
