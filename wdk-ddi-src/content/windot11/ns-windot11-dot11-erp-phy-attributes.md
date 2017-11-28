---
UID: NS.windot11.DOT11_ERP_PHY_ATTRIBUTES
title: DOT11_ERP_PHY_ATTRIBUTES
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_erp_phy_attributes.htm
old-project: netvista
ms.assetid: ce5f2833-7df6-449b-be68-ed58620fbb43
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: DOT11_ERP_PHY_ATTRIBUTES, DOT11_ERP_PHY_ATTRIBUTES, *PDOT11_ERP_PHY_ATTRIBUTES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating
   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_ERP_PHY_ATTRIBUTES
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
req.iface: 
req.product: Windows 10 or later.
---

# DOT11_ERP_PHY_ATTRIBUTES structure



## -description

## -syntax

````
typedef struct DOT11_ERP_PHY_ATTRIBUTES {
  DOT11_HRDSSS_PHY_ATTRIBUTES HRDSSSAttributes;
  BOOLEAN                     bERPPBCCOptionImplemented;
  BOOLEAN                     bDSSSOFDMOptionImplemented;
  BOOLEAN                     bShortSlotTimeOptionImplemented;
} DOT11_ERP_PHY_ATTRIBUTES, *PDOT11_ERP_PHY_ATTRIBUTES;
````


## -struct-fields
<dl>

### -field <b>HRDSSSAttributes</b>

<dd>
<p>Since the ERP PHY type is a superset of the high-rate direct-sequence spread spectrum (HRDSS) PHY
     type, the start of the DOT11_ERP_PHY_ATTRIBUTES structure is formatted as a 
     <a href="..\windot11\ns-windot11-dot11-hrdsss-phy-attributes.md">
     DOT11_HRDSSS_PHY_ATTRIBUTES</a> structure in order to define the HRDSS-specific attributes of the
     PHY.</p>
</dd>

### -field <b>bERPPBCCOptionImplemented</b>

<dd>
<p>A Boolean value that, if set to <b>TRUE</b>, specifies that the PHY supports enabled packet binary
     convolutional code (PBCC) modulation. 
     </p>
<p>For more information about PBCC modulation, refer to Clause 18.4.6.6 of the IEEE 802.11b-1999
     standard. For more information about the ERP-PBCC option, refer to Clause 19.6 of the IEEE 802.11g-2003
     standard.</p>
</dd>

### -field <b>bDSSSOFDMOptionImplemented</b>

<dd>
<p>A Boolean value that, if set to <b>TRUE</b>, specifies the PHY has enabled the use of the hybrid
     DSSS-OFDM modulation. If the 802.11 station supports this option, the PHY is capable of combining the
     direct-sequence spread spectrum (DSSS) preamble and header with the orthogonal frequency division
     multiplexing (OFDM) payload.
     </p>
<p>For more information about DSSS-OFDM modulation, refer to Clause 19.7 of the IEEE 802.11g-2003
     standard.</p>
</dd>

### -field <b>bShortSlotTimeOptionImplemented</b>

<dd>
<p>A Boolean value that, if set to <b>TRUE</b>, specifies the PHY supports the 802.11g short slot time
     option. For more information about the short slot time, refer to Clause 7.3.1.4 of the IEEE 802.11g-2003
     standard.</p>
</dd>
</dl>

## -remarks
<p>The miniport driver defines the attributes of a PHY on the 802.11 station through the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff548728">DOT11_PHY_ATTRIBUTES</a> structure, and
    formats the 
    <b>ERPAttributes</b> member as a DOT11_ERP_PHY_ATTRIBUTES structure. The driver must only do this if the
    PHY defined by the DOT11_PHY_ATTRIBUTES structure is an ERP PHY type.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating
   systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548643">DOT11_HRDSSS_PHY_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548728">DOT11_PHY_ATTRIBUTES</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_ERP_PHY_ATTRIBUTES structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
