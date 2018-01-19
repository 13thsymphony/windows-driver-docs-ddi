---
UID : NS:windot11._DOT11_EXTAP_ATTRIBUTES
title : _DOT11_EXTAP_ATTRIBUTES
author : windows-driver-content
description : Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location : netvista\dot11_extap_attributes.htm
old-project : netvista
ms.assetid : 0460357c-7180-45f0-a7ab-83c46c24ba68
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _DOT11_EXTAP_ATTRIBUTES, DOT11_EXTAP_ATTRIBUTES, *PDOT11_EXTAP_ATTRIBUTES
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : windot11.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows 7 and later versions of the Windows operating   systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DOT11_EXTAP_ATTRIBUTES
req.alt-loc : windot11.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : DOT11_EXTAP_ATTRIBUTES, *PDOT11_EXTAP_ATTRIBUTES
req.product : Windows 10 or later.
---

# _DOT11_EXTAP_ATTRIBUTES structure


## Syntax
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

## Members

        
            `bStrictlyOrderedServiceClassImplemented`

            A Boolean value that, if set to <b>TRUE</b>, specifies that the 802.11 station supports the IEEE 802.11
     StrictlyOrdered service class for media access control (MAC) service data unit (MSDU) packet delivery.
     

For more information about the StrictlyOrdered service class, refer to Clause 5.1.3 of the IEEE
     802.11-2012 standard.
        
            `Header`

            The type, revision, and size of the DOT11_EXTAP_ATTRIBUTES structure. This member is formatted as
     an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:
        
            `pInfraSupportedMcastAlgoPairs`

            A pointer to an array of authentication and cipher algorithms supported by the 802.11 station for
     sending and receiving multicast and broadcast packets in an infrastructure BSS network. Each entry in
     the array is formatted as a 
     <a href="..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md">
     DOT11_AUTH_CIPHER_PAIR</a> structure.
        
            `pInfraSupportedUcastAlgoPairs`

            A pointer to an array of authentication and cipher algorithms supported by the 802.11 station for
     sending and receiving unicast packets in an infrastructure BSS network. Each entry in the array is
     formatted as a 
     <a href="..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md">
     DOT11_AUTH_CIPHER_PAIR</a> structure.
        
            `pSupportedCountryOrRegionStrings`

            A pointer to an array of 802.11d country or region strings that are supported by the 802.11
     station. Each entry in the array is formatted as a 
     <a href="netvista.dot11_country_or_region_string">
     DOT11_COUNTRY_OR_REGION_STRING</a> structure.
        
            `uAssociationTableSize`

            The maximum number of associations that the 802.11 station can support simultaneously. The 802.11
     station must support an association list that has at least one entry. A NIC should typically be able to
     support at least 32 associations simultaneously.
     

If the NIC supports any authentication and cipher algorithms that require 
     <a href="https://msdn.microsoft.com/eed9effd-5c63-44ac-ab02-446f767feaea">key-Mapping keys</a>, it must support at least
     the number of entries in its key-mapping key table.
        
            `uDefaultKeyTableSize`

            The maximum number of cipher keys the 802.11 station supports for the default key and per-station
     default key tables.
     

For standard 802.11 cipher algorithms, the 802.11 station must support a table size of at least four
     cipher keys. For cipher algorithms developed by the independent hardware vendor (IHV), the table size
     can be four or greater.
        
            `uDesiredSSIDListSize`

            The maximum number of entries in the desired list of basic service set identifiers (BSSIDs)
     supported by the 802.11 station. The 802.11 station must support a BSSID list with at least one entry.
     

For more information about the desired BSSID list, see 
     <a href="netvista.oid_dot11_desired_bssid_list">
     OID_DOT11_DESIRED_BSSID_LIST</a>.
        
            `uInfraNumSupportedMcastAlgoPairs`

            The number of authentication and cipher algorithms supported by the 802.11 station for sending and
     receiving multicast and broadcast packets when configured for operation in an infrastructure basic
     service set (BSS) network. The 
     <b>uInfraNumSupportedMcastAlgoPairs</b> member must be the number of 
     <a href="..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md">DOT11_AUTH_CIPHER_PAIR</a> structures in
     the array referenced by the 
     <b>pInfraSupportedMcastAlgoPairs</b> member.
        
            `uInfraNumSupportedUcastAlgoPairs`

            The number of authentication and cipher algorithms supported by the 802.11 station for sending and
     receiving unicast packets when configured for operation in an infrastructure basic service set (BSS)
     network. The 
     <b>uInfraNumSupportedUcastAlgoPairs</b> member must be the number of 
     <a href="..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md">DOT11_AUTH_CIPHER_PAIR</a> structures in
     the array referenced by the 
     <b>pInfraSupportedUcastAlgoPairs</b> member.
        
            `uNumSupportedCountryOrRegionStrings`

            The number of country or region strings supported by the 802.11 station. If the 802.11 station
     supports multiple regulatory domains as specified by the IEEE 802.11d-2001 standard, each country or
     region string identifies a regulatory domain supported by the 802.11 station.
     

If the 802.11 station does not support the IEEE 802.11d-2001 standard, the miniport driver must set 
     <b>uNumSupportedCountryOrRegionStrings</b> to zero.
        
            `uPrivacyExemptionListSize`

            The maximum number of entries in the privacy exemption list supported by the 802.11 station. The
     802.11 station must support a privacy exemption list with at least one entry.
     

For more information about the privacy exemption list, see 
     <a href="netvista.oid_dot11_privacy_exemption_list">
     OID_DOT11_PRIVACY_EXEMPTION_LIST</a>.
        
            `uScanSSIDListSize`

            The maximum number of service set identifiers (SSIDs) supported by the 802.11 station for scan
     operations. The 802.11 station must support an SSID list of at least four entries.
     

The SSID list that the 802.11 station uses for scanning is specified when 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569413">OID_DOT11_SCAN_REQUEST</a> is
     set.
        
            `uWEPKeyValueMaxLength`

            The maximum length, in bytes, of a WEP cipher key supported by the 802.11 station.
     

The following table lists the minimum and maximum key lengths, in bytes, for the various WEP cipher
     values defined through 
     <a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a>.

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


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | windot11.h (include Ndis.h) |

    ## See Also

        <dl>
<dt>
<a href="..\wlantypes\ns-wlantypes-dot11_auth_cipher_pair.md">DOT11_AUTH_CIPHER_PAIR</a>
</dt>
<dt>
<a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a>
</dt>
<dt>
<a href="netvista.dot11_country_or_region_string">
   DOT11_COUNTRY_OR_REGION_STRING</a>
</dt>
<dt>
<a href="..\windot11\ns-windot11-_dot11_extap_attributes.md">DOT11_EXTAP_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_EXTAP_ATTRIBUTES structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>