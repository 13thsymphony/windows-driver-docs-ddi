---
UID: NS.dxgiddi.DXGI_DDI_RATIONAL
title: DXGI_DDI_RATIONAL
author: windows-driver-content
description: The DXGI_DDI_RATIONAL structure describes a fractional value that represents vertical and horizontal frequencies of a display mode (that is, vertical sync and horizontal sync).
old-location: display\dxgi_ddi_rational.htm
old-project: display
ms.assetid: 3a1ebeb8-4a0e-4a1f-9039-13ca8e375e5e
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGI_DDI_RATIONAL, DXGI_DDI_RATIONAL
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
req.alt-api: DXGI_DDI_RATIONAL
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
req.iface: 
---

# DXGI_DDI_RATIONAL structure



## -description
<p>The DXGI_DDI_RATIONAL structure describes a fractional value that represents vertical and horizontal frequencies of a display mode (that is, vertical sync and horizontal sync). </p>


## -syntax

````
typedef struct DXGI_DDI_RATIONAL {
  UINT Numerator;
  UINT Denominator;
} DXGI_DDI_RATIONAL;
````


## -struct-fields
<dl>

### -field Numerator

<dd>
<p>[in] The numerator of the frequency fraction.</p>
</dd>

### -field Denominator

<dd>
<p>[in] The denominator of the frequency fraction.</p>
</dd>
</dl>

## -remarks
<p>Vertical frequencies are stored in Hertz (Hz); horizontal frequencies are stored in kilohertz (kHz). The dynamic range of this encoding format, given 10^-7 resolution, is {0..(2^32 - 1) / 10^7}. This range translates to {0..428.4967296} [Hz] for vertical frequencies and {0..428.4967296} [kHz] for horizontal frequencies. This submicrosecond precision range is acceptable even for a provided application. (An error of one microsecond for video signal synchronization would imply a time drift with a cycle of 10^7/(60 x 60 x 24) = 115.741 days.)</p>

<p>For a rational number with a finite fractional sequence, use a denominator of the form 10^(length of fractional sequence). For a rational number without a finite fractional sequence, a sequence that exceeds the precision that the dynamic range of the denominator allows, or an irrational number, use an appropriate ratio of integers that best represents the value.</p>

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
<dt>Dxgiddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dxgiddi\ns-dxgiddi-dxgi-ddi-mode-desc.md">DXGI_DDI_MODE_DESC</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_RATIONAL structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
