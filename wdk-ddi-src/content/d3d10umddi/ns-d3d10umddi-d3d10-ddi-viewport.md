---
UID: NS.d3d10umddi.D3D10_DDI_VIEWPORT
title: D3D10_DDI_VIEWPORT
author: windows-driver-content
description: The D3D10_DDI_VIEWPORT structure describes a viewport.
old-location: display\d3d10_ddi_viewport.htm
old-project: display
ms.assetid: 5b2025ce-e0dd-434d-b92b-16ecaf24808f
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3D10_DDI_VIEWPORT, D3D10_DDI_VIEWPORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D10_DDI_VIEWPORT
req.alt-loc: d3d10umddi.h
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

# D3D10_DDI_VIEWPORT structure



## -description
<p>The D3D10_DDI_VIEWPORT structure describes a viewport.</p>


## -syntax

````
typedef struct D3D10_DDI_VIEWPORT {
  FLOAT TopLeftX;
  FLOAT TopLeftY;
  FLOAT Width;
  FLOAT Height;
  FLOAT MinDepth;
  FLOAT MaxDepth;
} D3D10_DDI_VIEWPORT;
````


## -struct-fields
<dl>

### -field <b>TopLeftX</b>

<dd>
<p>[in] A single-precision float vector for the top-left x-coordinate of the viewport.</p>
</dd>

### -field <b>TopLeftY</b>

<dd>
<p>[in] A single-precision float vector for the top-left y-coordinate of the viewport.</p>
</dd>

### -field <b>Width</b>

<dd>
<p>
      [in] A single-precision float vector for the width of the viewport.
     </p>
</dd>

### -field <b>Height</b>

<dd>
<p>[in] A single-precision float vector for the height of the viewport.</p>
</dd>

### -field <b>MinDepth</b>

<dd>
<p>[in] A single-precision float vector for the minimum depth of the viewport.</p>
</dd>

### -field <b>MaxDepth</b>

<dd>
<p>[in] A single-precision float vector for the maximum depth of the viewport.</p>
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
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-setviewports.md">SetViewports</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_VIEWPORT structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
