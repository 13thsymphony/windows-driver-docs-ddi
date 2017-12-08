---
UID: NS.WINDOT11.DOT11_OFDM_PHY_ATTRIBUTES
title: DOT11_OFDM_PHY_ATTRIBUTES
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_ofdm_phy_attributes.htm
old-project: netvista
ms.assetid: edc9bd9b-938f-43df-80fd-5a4d49f6f768
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: DOT11_OFDM_PHY_ATTRIBUTES, *PDOT11_OFDM_PHY_ATTRIBUTES, DOT11_OFDM_PHY_ATTRIBUTES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_OFDM_PHY_ATTRIBUTES
req.alt-loc: windot11.h
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
req.product: Windows 10 or later.
---

# DOT11_OFDM_PHY_ATTRIBUTES structure



## -description

## -syntax

````
typedef struct DOT11_OFDM_PHY_ATTRIBUTES {
  ULONG uFrequencyBandsSupported;
} DOT11_OFDM_PHY_ATTRIBUTES, *PDOT11_OFDM_PHY_ATTRIBUTES;
````


## -struct-fields

### -field uFrequencyBandsSupported

The frequency bands in which the PHY is capable of operating. Frequency bands are defined for:
     
<ul>
<li>
Unlicensed national information infrastructure (U-NII) bands.
</li>
<li>
Conference of European Post and Telecommunication (CEPT) bands.
</li>
<li>
Japan 5 GHz bands.
</li>
</ul>
The frequency bands supported by the PHY are defined through the following bitmask:
<table>
<tr>
<th>Bit</th>
<th>Description</th>
</tr>
<tr>
<td>
0
</td>
<td>
Can operate in the lower (5.15-5.25 GHz) U-NII band.
</td>
</tr>
<tr>
<td>
1
</td>
<td>
Can operate in the middle (5.25-5.35 GHz) U-NII band.
</td>
</tr>
<tr>
<td>
2
</td>
<td>
Can operate in the upper (5.725-5.825 GHz) U-NII band.
</td>
</tr>
<tr>
<td>
3
</td>
<td>
Can operate in CEPT B (5.47-5.7253 GHz) band.
</td>
</tr>
<tr>
<td>
4
</td>
<td>
Can operate in the lower Japan (5.15-5 5.25 GHz) band.
</td>
</tr>
<tr>
<td>
5
</td>
<td>
Can operate in the Japan 5.0 (5.03-8 5.091 GHz) band.
</td>
</tr>
<tr>
<td>
6
</td>
<td>
Can operate in the Japan 4.9 (4.9-5.0GHz) band.
</td>
</tr>
</table>
 

## -remarks
The miniport driver defines the attributes of a PHY on the 802.11 station through the 
    <a href="..\windot11\ns-windot11-dot11_phy_attributes.md">DOT11_PHY_ATTRIBUTES</a> structure, and
    formats the 
    <b>OFDMAttributes</b> member as a DOT11_OFDM_PHY_ATTRIBUTES structure. The miniport driver must only do this
    if the PHY defined by the DOT11_PHY_ATTRIBUTES structure is an OFDM PHY type.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating
   systems.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Windot11.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\windot11\ns-windot11-dot11_phy_attributes.md">DOT11_PHY_ATTRIBUTES</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_OFDM_PHY_ATTRIBUTES structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
