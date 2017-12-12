---
UID: NS.WINDOT11.DOT11_BSS_ENTRY
title: DOT11_BSS_ENTRY
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_bss_entry.htm
old-project: netvista
ms.assetid: 50661fc9-2f1f-4c9a-bc15-1cdf7c1f6d01
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: DOT11_BSS_ENTRY, DOT11_BSS_ENTRY, *PDOT11_BSS_ENTRY
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
req.alt-api: DOT11_BSS_ENTRY
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

# DOT11_BSS_ENTRY structure



## -description

## -syntax

````
typedef struct DOT11_BSS_ENTRY {
  ULONG                             uPhyId;
  DOT11_BSS_ENTRY_PHY_SPECIFIC_INFO PhySpecificInfo;
  DOT11_MAC_ADDRESS                 dot11BSSID;
  DOT11_BSS_TYPE                    dot11BSSType;
  LONG                              lRSSI;
  ULONG                             uLinkQuality;
  BOOLEAN                           bInRegDomain;
  USHORT                            usBeaconPeriod;
  ULONGLONG                         ullTimestamp;
  ULONGLONG                         ullHostTimestamp;
  USHORT                            usCapabilityInformation;
  ULONG                             uBufferLength;
  UCHAR                             ucBuffer[1];
} DOT11_BSS_ENTRY, *PDOT11_BSS_ENTRY;
````


## -struct-fields

### -field uPhyId

The identifier (ID) of the PHY that the 802.11 station used to detect the BSS network. The PHY ID
     is the index within the list of supported PHYs returned by the driver through a query of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569426">OID_DOT11_SUPPORTED_PHY_TYPES</a>.
     

This ID must not be DOT11_PHY_ID_ANY.


### -field PhySpecificInfo

The attributes of the PHY referenced by the 
     <b>uPhyId</b> member. 
     <b>PhySpecificInfo</b> is formatted as a 
     <a href="..\windot11\ns-windot11-dot11_bss_entry_phy_specific_info.md">
     DOT11_BSS_ENTRY_PHY_SPECIFIC_INFO</a> union.


### -field dot11BSSID

The media access control (MAC) address of the access point (AP) (for infrastructure BSS networks)
     or peer station (for independent BSS networks) that sent the 802.11 Beacon or Probe Response frame
     received by the 802.11 station while scanning. The data type for this member is the 
     <a href="netvista.dot11_mac_address">DOT11_MAC_ADDRESS</a> structure.


### -field dot11BSSType

The BSS network type. 
     

The data type for this member is the 
     <a href="netvista.dot11_bss_type">DOT11_BSS_TYPE</a> enumeration. The miniport
     driver must not set this member to the 
     <b>dot11_BSS_type_any</b> value.


### -field lRSSI

The received signal strength indicator (RSSI) value, in units of decibels referenced to 1.0
     milliwatts (dBm), as detected by the 802.11 station for the AP or peer station.


### -field uLinkQuality

The link quality value ranging from 0 through 100. A value of 100 specifies the highest link
     quality. For more information about determining the link quality, see 
     <a href="netvista.link_quality_operations">Link Quality Operations</a>.


### -field bInRegDomain

This member specifies whether the AP or peer station is operating within the regulatory domain as
     identified by the input country string. To set this member, the miniport driver must use the following
     guidelines:
     

<ul>
<li>
If the 802.11 station does not support multiple regulatory domains, set the member to <b>TRUE</b>. For
       more information about multiple regulatory domains, see 
       <a href="netvista.oid_dot11_multi_domain_capability_implemented">
       OID_DOT11_MULTI_DOMAIN_CAPABILITY_IMPLEMENTED</a>.

</li>
<li>
If the input country string is all zeros, set the member to <b>TRUE</b>.

</li>
<li>
If the AP or peer station is not operating on a channel that is valid for the regulatory domain
       specified by the input country string, set the member to <b>FALSE</b>.

</li>
<li>
If the 802.11 Beacon or Probe Response frame, which was received from the AP or peer station,
       doesn't include a Country information element (IE), set the member to <b>TRUE</b>.

For more information about the Country IE, refer to Clause 7.3.2.12 of the IEEE 802.11d-2001
       standard.

</li>
<li>
If the 802.11 Beacon or Probe Response frame, which was received from the AP or peer station, does
       include a Country IE, set the member to <b>FALSE</b> if the value of the Country String subfield does not
       equal the input country string.

</li>
<li>
Set the member to <b>TRUE</b> in all other cases.

</li>
</ul>

### -field usBeaconPeriod

The value of the Beacon Interval field from the 802.11 Beacon or Probe Response frame.


### -field ullTimestamp

The value of the Timestamp field from the 802.11 Beacon or Probe Response frame.


### -field ullHostTimestamp

The timestamp, resolved through a call to 
     <a href="netvista.ndisgetcurrentsystemtime">NdisGetCurrentSystemTime</a>, which
     records when the 802.11 station received the 802.11 Beacon or Probe Response frame.


### -field usCapabilityInformation

The value of the Capability Information field from the 802.11 Beacon or Probe Response
     frame.


### -field uBufferLength

The length, in bytes, of the 
     <b>ucBuffer</b> array in the DOT11_BSS_ENTRY structure. 
     <b>ulBufferLength</b> must be the exact length of the data in the 
     <b>ucBuffer</b> array and must not contain any padding for alignment.


### -field ucBuffer

The variable-length information elements (IEs) from the 802.11 Beacon or Probe Response frames.
     For each BSS, the IEs must be from the last Beacon or Probe Response frame received from that BSS
     network. If an IE is available in only one frame, the miniport driver must merge the IE with the other
     IEs from the last received Beacon or Probe Response frame.
     

When the NIC is in the Extensible Access Point (ExtAP) OP mode, the BSS list should contain an entry
     for the BSS that the NIC created.

For more information about the fields within IEEE 802.11 Beacon or Probe Response frames, refer to
     Clause 8.4 of the IEEE 802.11-2012 standard.


## -remarks
When the 802.11 station performs a scan operation, the Native 802.11 miniport driver caches the
    received 802.11 Beacon and Probe Response frames. For more information about the scan operation, see 
    <a href="netvista.native_802_11_scan_operations">Native 802.11 Scan
    Operations</a>.

After the 802.11 station completes the scan operation, the miniport driver returns the list of the
    cached Beacon and Probe Response frames when queried by 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569360">OID_DOT11_ENUM_BSS_LIST</a>. A separate
    DOT11_BSS_ENTRY structure is formatted for each Beacon and Probe Response frame.


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
<a href="netvista.dot11_bss_list">DOT11_BSS_LIST</a>
</dt>
<dt>
<a href="netvista.dot11_bss_type">DOT11_BSS_TYPE</a>
</dt>
<dt>
<a href="netvista.dot11_mac_address">DOT11_MAC_ADDRESS</a>
</dt>
<dt>
<a href="..\windot11\ns-windot11-dot11_bss_entry_phy_specific_info.md">
   DOT11_BSS_ENTRY_PHY_SPECIFIC_INFO</a>
</dt>
<dt>
<a href="netvista.ndisgetcurrentsystemtime">NdisGetCurrentSystemTime</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569360">OID_DOT11_ENUM_BSS_LIST</a>
</dt>
<dt>
<a href="netvista.oid_dot11_multi_domain_capability_implemented">
   OID_DOT11_MULTI_DOMAIN_CAPABILITY_IMPLEMENTED</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569426">OID_DOT11_SUPPORTED_PHY_TYPES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_BSS_ENTRY structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

