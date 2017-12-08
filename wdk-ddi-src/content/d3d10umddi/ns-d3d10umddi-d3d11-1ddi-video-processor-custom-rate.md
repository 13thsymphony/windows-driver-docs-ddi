---
UID: NS.d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_CUSTOM_RATE
title: D3D11_1DDI_VIDEO_PROCESSOR_CUSTOM_RATE
author: windows-driver-content
description: Specifies a custom rate for frame-rate conversion or inverse telecine (IVTC).
old-location: display\d3d11_1ddi_video_processor_custom_rate.htm
old-project: display
ms.assetid: d7ea23de-1d2d-4a76-aa99-0b18bf50654c
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_CUSTOM_RATE, D3D11_1DDI_VIDEO_PROCESSOR_CUSTOM_RATE
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
req.alt-api: D3D11_1DDI_VIDEO_PROCESSOR_CUSTOM_RATE
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
req.iface: 
---

# D3D11_1DDI_VIDEO_PROCESSOR_CUSTOM_RATE structure



## -description
<p>Specifies a custom rate for frame-rate conversion or inverse telecine (IVTC).</p>


## -syntax

````
typedef struct D3D11_1DDI_VIDEO_PROCESSOR_CUSTOM_RATE {
  DXGI_RATIONAL CustomRate;
  UINT          OutputFrames;
  BOOL          InputInterlaced;
  UINT          InputFramesOrFields;
} D3D11_1DDI_VIDEO_PROCESSOR_CUSTOM_RATE;
````


## -struct-fields
<dl>

### -field CustomRate

<dd>
<p>The ratio of the output frame rate to the input frame rate, expressed as a <a href="direct3ddxgi.dxgi_rational">DXGI_RATIONAL</a> structure that holds a rational number.</p>
</dd>

### -field OutputFrames

<dd>
<p>The number of output frames that will be generated for every <i>N</i> input samples, where <i>N</i> = <b>InputFramesOrFields</b>.</p>
</dd>

### -field InputInterlaced

<dd>
<p>If <b>TRUE</b>, the input stream must be interlaced. Otherwise, the input stream must be progressive.</p>
</dd>

### -field InputFramesOrFields

<dd>
<p>The number of input fields or frames for every <i>N</i> output frames that will be generated, where <i>N</i> = <b>OutputFrames</b>.</p>
</dd>
</dl>

## -remarks
<p>The <b>CustomRate</b> member gives the rate conversion factor, while the remaining members define the pattern of input and output samples.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="direct3ddxgi.dxgi_rational">DXGI_RATIONAL</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_VIDEO_PROCESSOR_CUSTOM_RATE structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
