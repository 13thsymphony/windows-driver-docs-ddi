---
UID: NS.WINDOT11.DOT11_EXTSTA_ATTRIBUTES~R1
title: DOT11_EXTSTA_ATTRIBUTES
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_extsta_attributes.htm
old-project: netvista
ms.assetid: 319017a7-f398-46f7-ab03-1dcb057c1332
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: DOT11_EXTSTA_ATTRIBUTES, *PDOT11_EXTSTA_ATTRIBUTES, DOT11_EXTSTA_ATTRIBUTES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_EXTSTA_ATTRIBUTES
req.alt-loc: Windot11.h
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

# DOT11_EXTSTA_ATTRIBUTES structure



## -description

## -syntax

````
typedef struct DOT11_EXTSTA_ATTRIBUTES {
  NDIS_OBJECT_HEADER              Header;
  ULONG                           uScanSSIDListSize;
  ULONG                           uDesiredBSSIDListSize;
  ULONG                           uDesiredSSIDListSize;
  ULONG                           uExcludedMacAddressListSize;
  ULONG                           uPrivacyExemptionListSize;
  ULONG                           uKeyMappingTableSize;
  ULONG                           uDefaultKeyTableSize;
  ULONG                           uWEPKeyValueMaxLength;
  ULONG                           uPMKIDCacheSize;
  ULONG                           uMaxNumPerSTADefaultKeyTables;
  BOOLEAN                         bStrictlyOrderedServiceClassImplemented;
  UCHAR                           ucSupportedQoSProtocolFlags;
  BOOLEAN                         bSafeModeImplemented;
  ULONG                           uNumSupportedCountryOrRegionStrings;
  PDOT11_COUNTRY_OR_REGION_STRING pSupportedCountryOrRegionStrings;
  ULONG                           uInfraNumSupportedUcastAlgoPairs;
  PDOT11_AUTH_CIPHER_PAIR         pInfraSupportedUcastAlgoPairs;
  ULONG                           uInfraNumSupportedMcastAlgoPairs;
  PDOT11_AUTH_CIPHER_PAIR         pInfraSupportedMcastAlgoPairs;
  ULONG                           uAdhocNumSupportedUcastAlgoPairs;
  PDOT11_AUTH_CIPHER_PAIR         pAdhocSupportedUcastAlgoPairs;
  ULONG                           uAdhocNumSupportedMcastAlgoPairs;
  PDOT11_AUTH_CIPHER_PAIR         pAdhocSupportedMcastAlgoPairs;
  BOOLEAN                         bAutoPowerSaveMode;
  ULONG                           uMaxNetworkOffloadListSize;
  BOOLEAN                         bMFPCapable;
  ULONG                           uInfraNumSupportedMcastMgmtAlgoPairs;
  PDOT11_AUTH_CIPHER_PAIR         pInfraSupportedMcastMgmtAlgoPairs;
} DOT11_EXTSTA_ATTRIBUTES, *PDOT11_EXTSTA_ATTRIBUTES;
````


## -struct-fields

### -field Header

The type, revision, and size of the <b>DOT11_EXTSTA_ATTRIBUTES</b> structure. This member is formatted as
     an 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values.




### -field Type

This member must be set to <b>NDIS_OBJECT_TYPE_DEFAULT</b>.


### -field Revision

This member must be set to one of the following values according to the operating system that
       the driver is intended to run on:
       




### -field DOT11_EXTSTA_ATTRIBUTES_REVISION_1

Windows Vista


### -field DOT11_EXTSTA_ATTRIBUTES_REVISION_2

Windows Vista with Service Pack 1 (SP1) or later versions of the Windows operating
         systems


### -field DOT11_EXTSTA_ATTRIBUTES_REVISION_3

Windows 8 or later versions of the Windows operating
         systems

</dd>
</dl>
These values determine how the operating system interprets the 
       <b>bSafeModeImplemented</b> member.


### -field Size

This member must be set to 
       <b>sizeof</b>(<b>DOT11_EXTSTA_ATTRIBUTES</b>).

</dd>
</dl>
For more information about these members, see 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field uScanSSIDListSize

The maximum number of service set identifiers (SSIDs) supported by the 802.11 station for scan
     operations. The 802.11 station must support an SSID list of at least four entries.
     

The SSID list that the 802.11 station uses for scanning is specified when 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569413">OID_DOT11_SCAN_REQUEST</a> is
     set.


### -field uDesiredBSSIDListSize

The maximum number of entries in the desired list of basic service set identifiers (BSSIDs)
     supported by the 802.11 station. The 802.11 station must support a BSSID list with at least one entry.
     

For more information about the desired BSSID list, see 
     <a href="netvista.oid_dot11_desired_bssid_list">
     OID_DOT11_DESIRED_BSSID_LIST</a>.


### -field uDesiredSSIDListSize

The maximum number of entries in the desired SSID list supported by the 802.11 station. The 802.11
     station must support a desired SSID list with at least one entry.
     

For more information about the desired SSID list, see 
     <a href="netvista.oid_dot11_desired_ssid_list">
     OID_DOT11_DESIRED_SSID_LIST</a>.


### -field uExcludedMacAddressListSize

The maximum number of entries in the excluded MAC address list supported by the 802.11 station.
     The 802.11 station must support an excluded MAC address list with at least four entries.
     

For more information about the desired excluded MAC address list, see 
     <a href="netvista.oid_dot11_excluded_mac_address_list">
     OID_DOT11_EXCLUDED_MAC_ADDRESS_LIST</a>.


### -field uPrivacyExemptionListSize

The maximum number of entries in the privacy exemption list supported by the 802.11 station. The
     802.11 station must support a privacy exemption list with at least one entry.
     

For more information about the privacy exemption list, see 
     <a href="netvista.oid_dot11_privacy_exemption_list">
     OID_DOT11_PRIVACY_EXEMPTION_LIST</a>.


### -field uKeyMappingTableSize

The maximum number of cipher key-mapping keys supported by the 802.11 station. It is recommended
     that the 802.11 station support at least 32 key-mapping keys.
     

For more information about key mapping keys, see 
     <a href="netvista.oid_dot11_cipher_key_mapping_key">
     OID_DOT11_CIPHER_KEY_MAPPING_KEY</a>.


### -field uDefaultKeyTableSize

The maximum number of cipher keys the 802.11 station supports for the default key and per-station
     default key tables.
     

For standard 802.11 cipher algorithms, the 802.11 station must support a table size of at least four
     cipher keys. For cipher algorithms developed by the independent hardware vendor (IHV), the table size
     can be four or greater.


### -field uWEPKeyValueMaxLength

The maximum length, in bytes, of a WEP cipher key supported by the 802.11 station.
     

The following table lists the minimum and maximum key lengths, in bytes, for the various WEP cipher
     values defined through 
     <a href="netvista.dot11_cipher_algorithm">DOT11_CIPHER_ALGORITHM</a>.

<table>
<tr>
<th>WEP cipher</th>
<th>Minimum key length</th>
<th>Maximum key length</th>
</tr>
<tr>
<td>
<b>DOT11_CIPHER_ALGO_WEP40</b>

</td>
<td>
5

</td>
<td>
5

</td>
</tr>
<tr>
<td>
<b>DOT11_CIPHER_ALGO_WEP104</b>

</td>
<td>
13

</td>
<td>
13

</td>
</tr>
<tr>
<td>
<b>DOT11_CIPHER_ALGO_WEP</b>

</td>
<td>
13

</td>
<td>
Any length supported by the 802.11 station

</td>
</tr>
</table>
 


### -field uPMKIDCacheSize

The maximum number of entries in the pairwise master key identifier (PMKID) cache supported by the
     802.11 station. 
     

If the 802.11 station does not support a PMKID cache, the miniport driver must set this member to
     zero. Otherwise, the 802.11 station must support a PMKID cache size of at least three entries.

For more information about the PMKID cache, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569400">OID_DOT11_PMKID_LIST</a>.


### -field uMaxNumPerSTADefaultKeyTables

The maximum number of per-station default cipher key tables supported by the 802.11 station. It is
     recommended that the 802.11 station support at least 32 per-station default cipher key tables.
     

For more information about per-station default cipher key tables, see 
     <a href="netvista.per_station_default_keys">Per-Station Default Keys</a>.


### -field bStrictlyOrderedServiceClassImplemented

A Boolean value that, if set to <b>TRUE</b>, specifies that the 802.11 station supports the IEEE 802.11
     StrictlyOrdered service class for media access control (MAC) service data unit (MSDU) packet delivery.
     

For more information about the StrictlyOrdered service class, refer to Clause 5.1.3 of the IEEE
     802.11-2012 standard.


### -field ucSupportedQoSProtocolFlags

A set of flags that specify the quality of service (QoS) protocols that the NIC implements. This
     member is either zero or a bitwise OR combination of the following flags:
     




### -field DOT11_QOS_PROTOCOL_FLAG_WMM

The NIC implements the 802.11 WMM QoS protocol.


### -field DOT11_QOS_PROTOCOL_FLAG_11E

The NIC implements the 802.11e QoS protocol.

</dd>
</dl>

### -field bSafeModeImplemented

The safe mode support capability of the NIC/miniport driver combination. The operating system
     interprets this member differently depending on the value of 
     <b>Header.Revision</b>:
     




### -field Revision = DOT11_EXTSTA_ATTRIBUTES_REVISION_1

The operating system interprets the 
       <b>bSafeModeImplemented</b> member as a Boolean value. If this value is <b>TRUE</b>, the NIC implements the
       802.11 safe mode of operation. Otherwise, the value is <b>FALSE</b>.


### -field Revision = DOT11_EXTSTA_ATTRIBUTES_REVISION_2 or higher

The operating system interprets the 
       <b>bSafeModeImplemented</b> member as a bit field with the following possible bit values set:
       

<ul>
<li>
If the bit field is set to <b>DOT11_EXTSTA_ATTRIBUTES_SAFEMODE_OID_SUPPORTED</b> with no other bits set,
         the miniport driver implements the 802.11 safe mode of operation.

</li>
<li>
If the bit field is set to <b>DOT11_EXTSTA_ATTRIBUTES_SAFEMODE_CERTIFIED</b>, the NIC/miniport
         combination has received a validation certificate from the National Institute of Standards and
         Technology (NIST) under Federal Information Processing Standards (FIPS) Publication 140-2, 
         <i>Security Requirements for Cryptographic Modules</i>.

</li>
</ul>
</dd>
</dl>
This member is used in conjunction with 
     <a href="netvista.oid_dot11_safe_mode_enabled">
     OID_DOT11_SAFE_MODE_ENABLED</a>.


### -field uNumSupportedCountryOrRegionStrings

The number of country or region strings supported by the 802.11 station. If the 802.11 station
     supports multiple regulatory domains as specified by the IEEE 802.11d-2001 standard, each country or
     region string identifies a regulatory domain supported by the 802.11 station.
     

If the 802.11 station does not support the IEEE 802.11d-2001 standard, the miniport driver must set 
     <b>uNumSupportedCountryOrRegionStrings</b> to zero.


### -field pSupportedCountryOrRegionStrings

A pointer to an array of 802.11d country or region strings that are supported by the 802.11
     station. Each entry in the array is formatted as a 
     <a href="netvista.dot11_country_or_region_string">
     DOT11_COUNTRY_OR_REGION_STRING</a> structure.


### -field uInfraNumSupportedUcastAlgoPairs

The number of authentication and cipher algorithms supported by the 802.11 station for sending and
     receiving unicast packets when configured for operation in an infrastructure basic service set (BSS)
     network. The 
     <b>uInfraNumSupportedUcastAlgoPairs</b> member must be the number of 
     <a href="..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md">DOT11_AUTH_CIPHER_PAIR</a> structures in
     the array referenced by the 
     <b>pInfraSupportedUcastAlgoPairs</b> member.


### -field pInfraSupportedUcastAlgoPairs

A pointer to an array of authentication and cipher algorithms supported by the 802.11 station for
     sending and receiving unicast packets in an infrastructure BSS network. Each entry in the array is
     formatted as a 
     <a href="..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md">
     DOT11_AUTH_CIPHER_PAIR</a> structure.


### -field uInfraNumSupportedMcastAlgoPairs

The number of authentication and cipher algorithms supported by the 802.11 station for sending and
     receiving multicast and broadcast packets when configured for operation in an infrastructure basic
     service set (BSS) network. The 
     <b>uInfraNumSupportedMcastAlgoPairs</b> member must be the number of 
     <a href="..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md">DOT11_AUTH_CIPHER_PAIR</a> structures in
     the array referenced by the 
     <b>pInfraSupportedMcastAlgoPairs</b> member.


### -field pInfraSupportedMcastAlgoPairs

A pointer to an array of authentication and cipher algorithms supported by the 802.11 station for
     sending and receiving multicast and broadcast packets in an infrastructure BSS network. Each entry in
     the array is formatted as a 
     <a href="..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md">
     DOT11_AUTH_CIPHER_PAIR</a> structure.


### -field uAdhocNumSupportedUcastAlgoPairs

The number of authentication and cipher algorithms supported by the 802.11 station for sending and
     receiving unicast packets when configured for operation in an independent BSS (IBSS) network. The 
     <b>uAdhocNumSupportedUcastAlgoPairs</b> member must be the number of 
     <a href="..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md">DOT11_AUTH_CIPHER_PAIR</a> structures in
     the array referenced by the 
     <b>pAdhocSupportedUcastAlgoPairs</b> member.


### -field pAdhocSupportedUcastAlgoPairs

A pointer to an array of authentication and cipher algorithms supported by the 802.11 station for
     sending and receiving unicast packets in an IBSS network. Each entry in the array is formatted as a 
     <a href="..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md">
     DOT11_AUTH_CIPHER_PAIR</a> structure.


### -field uAdhocNumSupportedMcastAlgoPairs

The number of authentication and cipher algorithms supported by the 802.11 station for sending and
     receiving multicast and broadcast packets when configured for operation in an IBSS network. The 
     <b>uAdhocNumSupportedMcastAlgoPairs</b> member must be the number of 
     <a href="..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md">DOT11_AUTH_CIPHER_PAIR</a> structures in
     the array referenced by the 
     <b>pAdhocSupportedMcastAlgoPairs</b> member.


### -field pAdhocSupportedMcastAlgoPairs

A pointer to an array of authentication and cipher algorithms supported by the 802.11 station for
     sending and receiving multicast and broadcast packets in an IBSS network. Each entry in the array is
     formatted as a 
     <a href="..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md">
     DOT11_AUTH_CIPHER_PAIR</a> structure.


### -field bAutoPowerSaveMode

The support capability of the NIC/miniport driver combination to autonomously manage power well, including detection and negotiation of proper Wi-Fi Power Save Mode (PSM) between the device and the Wi-Fi Access Point. NDIS 6.30 compliant Wi-Fi miniport drivers should set this member to TRUE.


### -field uMaxNetworkOffloadListSize

The maximum number of networks a miniport driver can offload, if it has the ability to support the Network List Offload capability.


### -field bMFPCapable

The support capability of the NIC/miniport driver to combination to support management frame protection between the device and the Wi-Fi Access Point  as specified in the 802.11w-2009 specification. Set to TRUE if supported. Otherwise, this member should be set to FALSE. 


### -field uInfraNumSupportedMcastMgmtAlgoPairs

The length of the array of authentication and cipher algorithm pairs pointed to in <b>pInfraSupportedMcastMgmtAlgoPairs</b>.


### -field pInfraSupportedMcastMgmtAlgoPairs

A pointer to an array of authentication and cipher algorithm pair which the device supports for MFP in Infra mode. The recommended cipher for Windows 8 is BIP with WPA or WPA2 authentication. Each entry in the array is
     formatted as a 
     <a href="..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md">
     DOT11_AUTH_CIPHER_PAIR</a> structure.


## -remarks
The 
    <a href="netvista.ndis_miniport_adapter_native_802_11_attributes">
    NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a> structure contains a member (<b>pExtSTAAttributes</b>) that specifies the address of a DOT11_EXTSTA_ATTRIBUTES structure. When the
    miniport driver calls 
    <a href="netvista.ndismsetminiportattributes">NdisMSetMiniportAttributes</a>,
    the driver sets the 
    <i>MiniportAttributes</i> parameter to the address of a driver-allocated block of memory which contains an
    NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES structure along with the DOT11_EXTSTA_ATTRIBUTES
    structure.

Management Frame Protection Required (MFPR) enforcement on Windows 8 is not supported. Hence miniport drivers should never set this bit in the RSN capabilities of RSN IE during an association request. For policy,  the access point may advertise MFPR which will allow MFP-capable STA to associate. Access points not supporting MFP capability will fail association. If MFPR is set by an access point and STA is not MFP capable, Windows 8 will treat the network as mismatched in capability and not send an association request to the miniport.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 8 and later versions of the Windows operating
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
<a href="..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md">DOT11_AUTH_CIPHER_PAIR</a>
</dt>
<dt>
<a href="netvista.dot11_cipher_algorithm">DOT11_CIPHER_ALGORITHM</a>
</dt>
<dt>
<a href="netvista.dot11_country_or_region_string">
   DOT11_COUNTRY_OR_REGION_STRING</a>
</dt>
<dt>
<a href="netvista.extensible_station_operation_mode">Extensible Station Operation
   Mode</a>
</dt>
<dt>
<a href="netvista.ndis_miniport_adapter_native_802_11_attributes">
   NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a>
</dt>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndismsetminiportattributes">NdisMSetMiniportAttributes</a>
</dt>
<dt>
<a href="netvista.oid_dot11_cipher_key_mapping_key">
   OID_DOT11_CIPHER_KEY_MAPPING_KEY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569141">OID_DOT11_DESIRED_BSSID_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569145">OID_DOT11_DESIRED_SSID_LIST</a>
</dt>
<dt>
<a href="netvista.oid_dot11_excluded_mac_address_list">
   OID_DOT11_EXCLUDED_MAC_ADDRESS_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569400">OID_DOT11_PMKID_LIST</a>
</dt>
<dt>
<a href="netvista.oid_dot11_privacy_exemption_list">
   OID_DOT11_PRIVACY_EXEMPTION_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569412">OID_DOT11_SAFE_MODE_ENABLED</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569413">OID_DOT11_SCAN_REQUEST</a>
</dt>
<dt>
<a href="netvista.per_station_default_keys">Per-Station Default Keys</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_EXTSTA_ATTRIBUTES structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

