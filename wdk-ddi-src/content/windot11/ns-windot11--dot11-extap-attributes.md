---
UID: NS.windot11._DOT11_EXTAP_ATTRIBUTES
title: DOT11_EXTAP_ATTRIBUTES
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_extap_attributes.htm
old-project: netvista
ms.assetid: 0460357c-7180-45f0-a7ab-83c46c24ba68
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: DOT11_EXTAP_ATTRIBUTES,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_EXTAP_ATTRIBUTES
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

# DOT11_EXTAP_ATTRIBUTES structure



## -description

## -syntax

````
typedef struct _DOT11_EXTAP_ATTRIBUTES {
  NDIS_OBJECT_HEADER              Header;
  ULONG                           uScanSSIDListSize;
  ULONG                           uDesiredSSIDListSize;
  ULONG                           uPrivacyExemptionListSize;
  ULONG                           uAssociationTableSize;
  ULONG                           uDefaultKeyTableSize;
  ULONG                           uWEPKeyValueMaxLength;
  BOOLEAN                         bStrictlyOrderedServiceClassImplemented;
  ULONG                           uNumSupportedCountryOrRegionStrings;
  PDOT11_COUNTRY_OR_REGION_STRING pSupportedCountryOrRegionStrings;
  ULONG                           uInfraNumSupportedUcastAlgoPairs;
  PDOT11_AUTH_CIPHER_PAIR         pInfraSupportedUcastAlgoPairs;
  ULONG                           uInfraNumSupportedMcastAlgoPairs;
  PDOT11_AUTH_CIPHER_PAIR         pInfraSupportedMcastAlgoPairs;
} DOT11_EXTAP_ATTRIBUTES, *PDOT11_EXTAP_ATTRIBUTES;
````


## -struct-fields
<dl>

### -field <b>Header</b>

<dd>
<p>The type, revision, and size of the DOT11_EXTAP_ATTRIBUTES structure. This member is formatted as
     an 
     <a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a> structure.
     </p>
<p>The miniport driver must set the members of 
     <b>Header</b> to the following values:</p>
<p></p>
<dl>

### -field <a id="Type"></a><a id="type"></a><a id="TYPE"></a>Type

<dd>
<p>This member must be set to NDIS_OBJECT_TYPE_DEFAULT.</p>
</dd>

### -field <a id="Revision"></a><a id="revision"></a><a id="REVISION"></a>Revision

<dd>
<p>This member must be set to DOT11_EXTAP_ATTRIBUTES_REVISION_1.</p>
</dd>

### -field <a id="Size"></a><a id="size"></a><a id="SIZE"></a>Size

<dd>
<p>This member must be set to 
       <b>sizeof</b>(DOT11_EXTAP_ATTRIBUTES).</p>
</dd>
</dl>
<p>For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a>.</p>
</dd>

### -field <b>uScanSSIDListSize</b>

<dd>
<p>The maximum number of service set identifiers (SSIDs) supported by the 802.11 station for scan
     operations. The 802.11 station must support an SSID list of at least four entries.
     </p>
<p>The SSID list that the 802.11 station uses for scanning is specified when 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569413">OID_DOT11_SCAN_REQUEST</a> is
     set.</p>
</dd>

### -field <b>uDesiredSSIDListSize</b>

<dd>
<p>The maximum number of entries in the desired list of basic service set identifiers (BSSIDs)
     supported by the 802.11 station. The 802.11 station must support a BSSID list with at least one entry.
     </p>
<p>For more information about the desired BSSID list, see 
     <a href="netvista.oid_dot11_desired_bssid_list">
     OID_DOT11_DESIRED_BSSID_LIST</a>.</p>
</dd>

### -field <b>uPrivacyExemptionListSize</b>

<dd>
<p>The maximum number of entries in the privacy exemption list supported by the 802.11 station. The
     802.11 station must support a privacy exemption list with at least one entry.
     </p>
<p>For more information about the privacy exemption list, see 
     <a href="netvista.oid_dot11_privacy_exemption_list">
     OID_DOT11_PRIVACY_EXEMPTION_LIST</a>.</p>
</dd>

### -field <b>uAssociationTableSize</b>

<dd>
<p>The maximum number of associations that the 802.11 station can support simultaneously. The 802.11
     station must support an association list that has at least one entry. A NIC should typically be able to
     support at least 32 associations simultaneously.
     </p>
<p>If the NIC supports any authentication and cipher algorithms that require 
     <a href="NULL">key-Mapping keys</a>, it must support at least
     the number of entries in its key-mapping key table.</p>
</dd>

### -field <b>uDefaultKeyTableSize</b>

<dd>
<p>The maximum number of cipher keys the 802.11 station supports for the default key and per-station
     default key tables.
     </p>
<p>For standard 802.11 cipher algorithms, the 802.11 station must support a table size of at least four
     cipher keys. For cipher algorithms developed by the independent hardware vendor (IHV), the table size
     can be four or greater.</p>
</dd>

### -field <b>uWEPKeyValueMaxLength</b>

<dd>
<p>The maximum length, in bytes, of a WEP cipher key supported by the 802.11 station.
     </p>
<p>The following table lists the minimum and maximum key lengths, in bytes, for the various WEP cipher
     values defined through 
     <a href="..\wlantypes\ne-wlantypes--dot11-cipher-algorithm.md">DOT11_CIPHER_ALGORITHM</a>.</p>
<table>
<tr>
<th>
        WEP cipher
        
       </th>
<th>
        Minimum key length
        
       </th>
<th>
        Maximum key length
        
       </th>
</tr>
<tr>
<td>
<p><b>DOT11_CIPHER_ALGO_WEP40</b></p>
</td>
<td>
<p>5</p>
</td>
<td>
<p>5</p>
</td>
</tr>
<tr>
<td>
<p><b>DOT11_CIPHER_ALGO_WEP104</b></p>
</td>
<td>
<p>13</p>
</td>
<td>
<p>13</p>
</td>
</tr>
<tr>
<td>
<p><b>DOT11_CIPHER_ALGO_WEP</b></p>
</td>
<td>
<p>13</p>
</td>
<td>
<p>Any length supported by the 802.11 station</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field <b>bStrictlyOrderedServiceClassImplemented</b>

<dd>
<p>A Boolean value that, if set to <b>TRUE</b>, specifies that the 802.11 station supports the IEEE 802.11
     StrictlyOrdered service class for media access control (MAC) service data unit (MSDU) packet delivery.
     </p>
<p>For more information about the StrictlyOrdered service class, refer to Clause 5.1.3 of the IEEE
     802.11-2012 standard.</p>
</dd>

### -field <b>uNumSupportedCountryOrRegionStrings</b>

<dd>
<p>The number of country or region strings supported by the 802.11 station. If the 802.11 station
     supports multiple regulatory domains as specified by the IEEE 802.11d-2001 standard, each country or
     region string identifies a regulatory domain supported by the 802.11 station.
     </p>
<p>If the 802.11 station does not support the IEEE 802.11d-2001 standard, the miniport driver must set 
     <b>uNumSupportedCountryOrRegionStrings</b> to zero.</p>
</dd>

### -field <b>pSupportedCountryOrRegionStrings</b>

<dd>
<p>A pointer to an array of 802.11d country or region strings that are supported by the 802.11
     station. Each entry in the array is formatted as a 
     <a href="netvista.dot11_country_or_region_string">
     DOT11_COUNTRY_OR_REGION_STRING</a> structure.</p>
</dd>

### -field <b>uInfraNumSupportedUcastAlgoPairs</b>

<dd>
<p>The number of authentication and cipher algorithms supported by the 802.11 station for sending and
     receiving unicast packets when configured for operation in an infrastructure basic service set (BSS)
     network. The 
     <b>uInfraNumSupportedUcastAlgoPairs</b> member must be the number of 
     <a href="..\wlantypes\ns-wlantypes-dot11-auth-cipher-pair.md">DOT11_AUTH_CIPHER_PAIR</a> structures in
     the array referenced by the 
     <b>pInfraSupportedUcastAlgoPairs</b> member.</p>
</dd>

### -field <b>pInfraSupportedUcastAlgoPairs</b>

<dd>
<p>A pointer to an array of authentication and cipher algorithms supported by the 802.11 station for
     sending and receiving unicast packets in an infrastructure BSS network. Each entry in the array is
     formatted as a 
     <a href="..\wlantypes\ns-wlantypes-dot11-auth-cipher-pair.md">
     DOT11_AUTH_CIPHER_PAIR</a> structure.</p>
</dd>

### -field <b>uInfraNumSupportedMcastAlgoPairs</b>

<dd>
<p>The number of authentication and cipher algorithms supported by the 802.11 station for sending and
     receiving multicast and broadcast packets when configured for operation in an infrastructure basic
     service set (BSS) network. The 
     <b>uInfraNumSupportedMcastAlgoPairs</b> member must be the number of 
     <a href="..\wlantypes\ns-wlantypes-dot11-auth-cipher-pair.md">DOT11_AUTH_CIPHER_PAIR</a> structures in
     the array referenced by the 
     <b>pInfraSupportedMcastAlgoPairs</b> member.</p>
</dd>

### -field <b>pInfraSupportedMcastAlgoPairs</b>

<dd>
<p>A pointer to an array of authentication and cipher algorithms supported by the 802.11 station for
     sending and receiving multicast and broadcast packets in an infrastructure BSS network. Each entry in
     the array is formatted as a 
     <a href="..\wlantypes\ns-wlantypes-dot11-auth-cipher-pair.md">
     DOT11_AUTH_CIPHER_PAIR</a> structure.</p>
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
<p>Available in Windows 7 and later versions of the Windows operating
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
<a href="..\wlantypes\ns-wlantypes-dot11-auth-cipher-pair.md">DOT11_AUTH_CIPHER_PAIR</a>
</dt>
<dt>
<a href="..\wlantypes\ne-wlantypes--dot11-cipher-algorithm.md">DOT11_CIPHER_ALGORITHM</a>
</dt>
<dt>
<a href="netvista.dot11_country_or_region_string">
   DOT11_COUNTRY_OR_REGION_STRING</a>
</dt>
<dt>
<a href="..\windot11\ns-windot11--dot11-extap-attributes.md">DOT11_EXTAP_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569141">OID_DOT11_DESIRED_BSSID_LIST</a>
</dt>
<dt>
<a href="netvista.oid_dot11_privacy_exemption_list">
   OID_DOT11_PRIVACY_EXEMPTION_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569413">OID_DOT11_SCAN_REQUEST</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_EXTAP_ATTRIBUTES structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
