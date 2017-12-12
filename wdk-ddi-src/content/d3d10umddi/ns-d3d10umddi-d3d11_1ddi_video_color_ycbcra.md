---
UID: NS.D3D10UMDDI.D3D11_1DDI_VIDEO_COLOR_YCBCRA
title: D3D11_1DDI_VIDEO_COLOR_YCbCrA
author: windows-driver-content
description: Specifies a YCbCr color value.
old-location: display\d3d11_1ddi_video_color_ycbcra.htm
old-project: display
ms.assetid: d6d8147e-8cc8-4c35-8031-bce2fa3ccd67
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: D3D11_1DDI_VIDEO_COLOR_YCbCrA, D3D11_1DDI_VIDEO_COLOR_YCbCrA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D11_1DDI_VIDEO_COLOR_YCbCrA
req.alt-loc: D3d10umddi.h
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

# D3D11_1DDI_VIDEO_COLOR_YCbCrA structure



## -description
Specifies a YCbCr color value.



## -syntax

````
typedef struct D3D11_1DDI_VIDEO_COLOR_YCbCrA {
  float Y;
  float Cb;
  float Cr;
  float A;
} D3D11_1DDI_VIDEO_COLOR_YCbCrA;
````


## -struct-fields

### -field Y

The Y (luma) value.


### -field Cb

The Cb chroma value.


### -field Cr

The Cr chroma value.


### -field A

The alpha value. Values range from 0 (transparent) to 1 (opaque).


## -remarks
Values have a nominal range of [0...1]. Given a format with  <i>n</i> bits per channel, the value of each color component is calculated as follows:

<code>val = f * ((1 &lt;&lt; n)-1)</code>

For example, for 8-bit YUV formats, <code>val = BYTE(f * 255.0)</code>.  Reference black is (0.0625, 0.5, 0.5), which corresponds to (16, 128, 128) in an 8-bit representation.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>