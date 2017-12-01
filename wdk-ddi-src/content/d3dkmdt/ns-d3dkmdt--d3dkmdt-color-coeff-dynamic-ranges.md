---
UID: NS.d3dkmdt._D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES
title: D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES
author: windows-driver-content
description: The D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES contains values that indicate the dynamic range of each color channel of a video present target or a monitor.
old-location: display\d3dkmdt_color_coeff_dynamic_ranges.htm
old-project: display
ms.assetid: 7fdd1d52-c406-4da7-adff-4300e795be00
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES
req.alt-loc: d3dkmdt.h
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

# D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES structure



## -description
<p>The D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES contains values that indicate the dynamic range of each color channel of a video present target or a monitor.</p>


## -syntax

````
typedef struct _D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES {
  UINT FirstChannel;
  UINT SecondChannel;
  UINT ThirdChannel;
  UINT FourthChannel;
} D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES;
````


## -struct-fields
<dl>

### -field <b>FirstChannel</b>

<dd>
<p>The bit depth of the first color channel.</p>
</dd>

### -field <b>SecondChannel</b>

<dd>
<p>The bit depth of the second color channel.</p>
</dd>

### -field <b>ThirdChannel</b>

<dd>
<p>The bit depth of the third color channel.</p>
</dd>

### -field <b>FourthChannel</b>

<dd>
<p>Reserved.</p>
</dd>
</dl>

## -remarks
<p>The <b>VidPnTargetColorCoeffDynamicRanges</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt--d3dkmdt-vidpn-present-path.md">D3DKMDT_VIDPN_PRESENT_PATH</a> structure is a D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES structure.</p>

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
<dt>D3dkmdt.h (include D3dkmdt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmdt\ne-d3dkmdt--d3dkmdt-color-basis.md">D3DKMDT_COLOR_BASIS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
