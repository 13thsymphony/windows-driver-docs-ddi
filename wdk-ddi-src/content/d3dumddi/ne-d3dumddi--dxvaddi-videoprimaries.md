---
UID: NE.d3dumddi._DXVADDI_VIDEOPRIMARIES
title: DXVADDI_VIDEOPRIMARIES
author: windows-driver-content
description: The DXVADDI_VIDEOPRIMARIES enumeration type contains values that identify the color primaries, which state which RGB basis functions are used.
old-location: display\dxvaddi_videoprimaries.htm
old-project: display
ms.assetid: d7049f38-78a7-42bf-a1a5-5d35fe70ae15
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_MIRACAST_CHUNK_INFO, DXGK_MIRACAST_CHUNK_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVADDI_VIDEOPRIMARIES
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

# DXVADDI_VIDEOPRIMARIES enumeration



## -description
<p>The DXVADDI_VIDEOPRIMARIES enumeration type contains values that identify the color primaries, which state which RGB basis functions are used.</p>


## -syntax

````
typedef enum _DXVADDI_VIDEOPRIMARIES { 
  DXVADDI_VideoPrimariesMask            = 0x001f,
  DXVADDI_VideoPrimaries_Unknown        = 0,
  DXVADDI_VideoPrimaries_reserved       = 1,
  DXVADDI_VideoPrimaries_BT709          = 2,
  DXVADDI_VideoPrimaries_BT470_2_SysM   = 3,
  DXVADDI_VideoPrimaries_BT470_2_SysBG  = 4,
  DXVADDI_VideoPrimaries_SMPTE170M      = 5,
  DXVADDI_VideoPrimaries_SMPTE240M      = 6,
  DXVADDI_VideoPrimaries_EBU3213        = 7,
  DXVADDI_VideoPrimaries_SMPTE_C        = 8
} DXVADDI_VIDEOPRIMARIES;
````


## -enum-fields
<dl>

### -field <a id="DXVADDI_VideoPrimariesMask"></a><a id="dxvaddi_videoprimariesmask"></a><a id="DXVADDI_VIDEOPRIMARIESMASK"></a><b>DXVADDI_VideoPrimariesMask</b>

<dd>
<p>Specifies the color primaries mask. The first 5 (0x001F) bits of a DWORD can be used to specify color primaries.</p>
</dd>

### -field <a id="DXVADDI_VideoPrimaries_Unknown"></a><a id="dxvaddi_videoprimaries_unknown"></a><a id="DXVADDI_VIDEOPRIMARIES_UNKNOWN"></a><b>DXVADDI_VideoPrimaries_Unknown</b>

<dd>
<p>Specifies that color primaries are not specified. The default is BT709.</p>
</dd>

### -field <a id="DXVADDI_VideoPrimaries_reserved"></a><a id="dxvaddi_videoprimaries_reserved"></a><a id="DXVADDI_VIDEOPRIMARIES_RESERVED"></a><b>DXVADDI_VideoPrimaries_reserved</b>

<dd>
<p>[in] Reserved. Do not use this value.</p>
</dd>

### -field <a id="DXVADDI_VideoPrimaries_BT709"></a><a id="dxvaddi_videoprimaries_bt709"></a><a id="DXVADDI_VIDEOPRIMARIES_BT709"></a><b>DXVADDI_VideoPrimaries_BT709</b>

<dd>
<p>Specifies BT709 primaries (including sRGB and scRGB).</p>
</dd>

### -field <a id="DXVADDI_VideoPrimaries_BT470_2_SysM"></a><a id="dxvaddi_videoprimaries_bt470_2_sysm"></a><a id="DXVADDI_VIDEOPRIMARIES_BT470_2_SYSM"></a><b>DXVADDI_VideoPrimaries_BT470_2_SysM</b>

<dd>
<p>Specifies BT470-2 SysM primaries, which are the original NTSC primaries. </p>
</dd>

### -field <a id="DXVADDI_VideoPrimaries_BT470_2_SysBG"></a><a id="dxvaddi_videoprimaries_bt470_2_sysbg"></a><a id="DXVADDI_VIDEOPRIMARIES_BT470_2_SYSBG"></a><b>DXVADDI_VideoPrimaries_BT470_2_SysBG</b>

<dd>
<p>Specifies BT470-2 SysBG primaries. </p>
</dd>

### -field <a id="DXVADDI_VideoPrimaries_SMPTE170M"></a><a id="dxvaddi_videoprimaries_smpte170m"></a><a id="DXVADDI_VIDEOPRIMARIES_SMPTE170M"></a><b>DXVADDI_VideoPrimaries_SMPTE170M</b>

<dd>
<p>Specifies SMPTE170M primaries, which are rarely used analog NTSC primaries (also known as SMPTE RP 145).</p>
</dd>

### -field <a id="DXVADDI_VideoPrimaries_SMPTE240M"></a><a id="dxvaddi_videoprimaries_smpte240m"></a><a id="DXVADDI_VIDEOPRIMARIES_SMPTE240M"></a><b>DXVADDI_VideoPrimaries_SMPTE240M</b>

<dd>
<p>Specifies SMPTE240M primaries. </p>
</dd>

### -field <a id="DXVADDI_VideoPrimaries_EBU3213"></a><a id="dxvaddi_videoprimaries_ebu3213"></a><a id="DXVADDI_VIDEOPRIMARIES_EBU3213"></a><b>DXVADDI_VideoPrimaries_EBU3213</b>

<dd>
<p>Specifies EBU3213 primaries. </p>
</dd>

### -field <a id="DXVADDI_VideoPrimaries_SMPTE_C"></a><a id="dxvaddi_videoprimaries_smpte_c"></a><a id="DXVADDI_VIDEOPRIMARIES_SMPTE_C"></a><b>DXVADDI_VideoPrimaries_SMPTE_C</b>

<dd>
<p>Specifies SMPTE_C primaries, which are analog '79 NTSC primaries.</p>
</dd>
</dl>

## -remarks
<p>One of the values of DXVADDI_VIDEOPRIMARIES can be specified in the <b>VideoPrimaries</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562904">DXVADDI_EXTENDEDFORMAT</a> structure.</p>

<p>One of the values of DXVADDI_VIDEOPRIMARIES can be specified in the <b>VideoPrimaries</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562904">DXVADDI_EXTENDEDFORMAT</a> structure.</p>

<p>One of the values of DXVADDI_VIDEOPRIMARIES can be specified in the <b>VideoPrimaries</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562904">DXVADDI_EXTENDEDFORMAT</a> structure.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562904">DXVADDI_EXTENDEDFORMAT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_VIDEOPRIMARIES enumeration%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
