---
UID: NS.WINDOT11.DOT11_BSS_ENTRY_PHY_SPECIFIC_INFO
title: DOT11_BSS_ENTRY_PHY_SPECIFIC_INFO
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_bss_entry_phy_specific_info.htm
old-project: NetVista
ms.assetid: 85bcd355-633b-4d3f-a387-1e3b2ac3a013
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: DOT11_BSS_ENTRY_PHY_SPECIFIC_INFO, *PDOT11_BSS_ENTRY_PHY_SPECIFIC_INFO, DOT11_BSS_ENTRY_PHY_SPECIFIC_INFO, PDOT11_BSS_ENTRY_PHY_SPECIFIC_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Wlclient.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_BSS_ENTRY_PHY_SPECIFIC_INFO
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

# DOT11_BSS_ENTRY_PHY_SPECIFIC_INFO structure



## -description

## -syntax

````
typedef union DOT11_BSS_ENTRY_PHY_SPECIFIC_INFO {
  ULONG  uChCenterFrequency;
  struct {
    ULONG uHopPattern;
    ULONG uHopSet;
    ULONG uDwellTime;
  } FHSS;
} DOT11_BSS_ENTRY_PHY_SPECIFIC_INFO, *PDOT11_BSS_ENTRY_PHY_SPECIFIC_INFO;
````


## -struct-fields

### -field uChCenterFrequency

The channel center frequency of the band on which the 802.11 Probe-Response or Beacon frame was
     received. The value of 
     <b>uChCenterFrequency</b> is in units of megahertz (MHz). 
     

<div class="alert"><b>Note</b>  This member is only valid for PHY types that are not frequency-hopping spread
     spectrum (FHSS).</div>
<div> </div>

### -field FHSS

The FHSS parameters, as specified by the following members:


### -field uHopPattern

The current hopping pattern used by the layer management entity (LME) of the PHY to determine the
      hopping sequence. For more information about how the hopping sequence is determined, refer to Clause
      14.9.2.20 of the IEEE 802.11-2012 standard.
      

<div class="alert"><b>Note</b>  This member is only valid for FHSS PHY types.</div>
<div> </div>

### -field uHopSet

The current set of patterns used by the LME of the PHY to determine the hopping sequence. For
      more information about the hopping pattern sets, refer to Clause 14.9.2.19 of the IEEE 802.11-2012
      standard.
      

<div class="alert"><b>Note</b>  This member is only valid for FHSS PHY types.</div>
<div> </div>

### -field uDwellTime

The maximum amount of time that the PHY can use when transmitting on a single channel. The value
      of 
      <b>uDwellTime</b> is in units of 802.11 time units (TU). One TU is 1024 microseconds.
      

<div class="alert"><b>Note</b>  This member is only valid for FHSS PHY types.</div>
<div> </div>
</dd>
</dl>

## -remarks
The DOT11_BSS_ENTRY_PHY_SPECIFIC_INFO union is a member of the 
    <a href="..\windot11\ns-windot11-dot11_bss_entry.md">DOT11_BSS_ENTRY</a> structure.


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
<dt>Windot11.h (include Wlclient.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\windot11\ns-windot11-dot11_bss_entry.md">DOT11_BSS_ENTRY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20DOT11_BSS_ENTRY_PHY_SPECIFIC_INFO union%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

