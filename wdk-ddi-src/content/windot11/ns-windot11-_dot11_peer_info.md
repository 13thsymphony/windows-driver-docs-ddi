---
UID: NS.WINDOT11._DOT11_PEER_INFO
title: _DOT11_PEER_INFO
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_peer_info.htm
old-project: NetVista
ms.assetid: f1d5bbd9-45e3-4802-ab9b-77ff6bdcd6ec
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _DOT11_PEER_INFO, DOT11_PEER_INFO, *PDOT11_PEER_INFO
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
req.alt-api: DOT11_PEER_INFO
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

# _DOT11_PEER_INFO structure



## -description

## -syntax

````
typedef struct _DOT11_PEER_INFO {
  DOT11_MAC_ADDRESS       MacAddress;
  USHORT                  usCapabilityInformation;
  DOT11_AUTH_ALGORITHM    AuthAlgo;
  DOT11_CIPHER_ALGORITHM  UnicastCipherAlgo;
  DOT11_CIPHER_ALGORITHM  MulticastCipherAlgo;
  BOOLEAN                 bWpsEnabled;
  USHORT                  usListenInterval;
  UCHAR                   ucSupportedRates[MAX_NUM_SUPPORTED_RATES_V2];
  USHORT                  usAssociationID;
  DOT11_ASSOCIATION_STATE AssociationState;
  DOT11_POWER_MODE        PowerMode;
  LARGE_INTEGER           liAssociationUpTime;
  DOT11_PEER_STATISTICS   Statistics;
} DOT11_PEER_INFO, *PDOT11_PEER_INFO;
````


## -struct-fields

### -field MacAddress

The media access control (MAC) address of the peer station within an independent BSS (IBSS)
     network.


### -field usCapabilityInformation

The 802.11 Capability Information field from the beacon or probe response frames that the 802.11
     station most recently received from the peer.


### -field AuthAlgo

The authentication algorithm that the 802.11 station resolved with the peer station during the
     association operation. For more information about the data type for the 
     <b>AuthAlgo</b> member, see 
     <a href="netvista.dot11_auth_algorithm">DOT11_AUTH_ALGORITHM</a>.
     

This member is not defined if the peer is not associated.


### -field UnicastCipherAlgo

The unicast cipher algorithm that the 802.11 station resolved with the peer station during the
     association operation. For more information about the data type for the 
     <b>UnicastCipherAlgo</b> member, see 
     <a href="netvista.dot11_cipher_algorithm">DOT11_CIPHER_ALGORITHM</a>.
     

This member is not defined if the peer is not associated.


### -field MulticastCipherAlgo

The multicast cipher algorithm that the 802.11 station resolved with the peer station during the
     association operation. For more information about the data type for the 
     <b>MulticastCipherAlgo</b> member, see 
     <a href="netvista.dot11_cipher_algorithm">DOT11_CIPHER_ALGORITHM</a>.
     

This member is not defined if the peer is not associated.


### -field bWpsEnabled

A Boolean value that indicates whether WiFi Protected Setup (WPS) is enabled for the peer station.
     If <b>TRUE</b>, WPS is enabled, and the authentication and cipher algorithms that are used by the peer might be
     different from the algorithms that are enabled on the AP.
     

This member should not be used if the peer is not associated.


### -field usListenInterval

A USHORT value that defines the 802.11 Listen Interval field that was obtained from the
     association request.
     

This member has a value of zero if the peer is not associated.


### -field ucSupportedRates

A UCHAR value that specifies the data rates supported by the peer station. These rates are based
     on the 802.11 Supported Rates IE from the beacon or probe response frames that the 802.11 station most
     recently received from the peer.
     

Each entry in the 
     <b>ucPeerSupportedRates</b> array is the value of an index within the table of data rates returned
     through a query of 
     <a href="netvista.oid_dot11_data_rate_mapping_table">
     OID_DOT11_DATA_RATE_MAPPING_TABLE</a>. The index value must be between 2 and 127.

This member has a value of zero if the peer is not associated.


### -field usAssociationID

A USHORT value that specifies the 802.11 Association ID field from the association or
     re-association response frames that the 802.11 station received from the AP.
     

This member has a value of 0xFFFF if the peer is not associated.


### -field AssociationState

A 
     <a href="netvista.dot11_association_state">DOT11_ASSOCIATION_STATE</a>-type value
     that indicates the 802.11 authentication and association state of the peer station. The state can be
     either 
     <b>dot11_assoc_state_auth_unassoc</b> or 
     <b>dot11_assoc_state_auth_assoc</b>.
     

In the 
     <i>IEEE 802.11 Standard</i>, the 802.11 authentication procedure is optional for an independent network.
     Therefore, depending upon the IHV implementation, the state represented by the 
     <b>dot11_assoc_state_auth_unassoc</b> enumeration value may not be applicable.


### -field PowerMode

A 
     <a href="netvista.dot11_power_mode">DOT11_POWER_MODE</a>-type value that describes
     the latest power management mode of the peer station.


### -field liAssociationUpTime

A LARGEINTEGER value that specifies the timestamp when the 802.11 association procedure successfully
     completed. The miniport driver calls 
     <a href="netvista.ndisgetcurrentsystemtime">NdisGetCurrentSystemTime</a> to get
     the timestamp of the association completion.
     

This member has a value of zero if the peer is not associated.


### -field Statistics

The statistics counters for data traffic, defined by the 
     <a href="netvista.dot11_peer_statistics">DOT11_PEER_STATISTICS</a> structure.
     

This member has a value of zero if the peer is not associated.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 7 and later versions of the Windows operating
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
<a href="netvista.dot11_association_state">DOT11_ASSOCIATION_STATE</a>
</dt>
<dt>
<a href="netvista.dot11_peer_info_list">DOT11_PEER_INFO_LIST</a>
</dt>
<dt>
<a href="netvista.dot11_peer_statistics">DOT11_PEER_STATISTICS</a>
</dt>
<dt>
<a href="netvista.dot11_power_mode">DOT11_POWER_MODE</a>
</dt>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndisgetcurrentsystemtime">NdisGetCurrentSystemTime</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20DOT11_PEER_INFO structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

