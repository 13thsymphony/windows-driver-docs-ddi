---
UID: NE.fwpsk.FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET_
title: FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET_
author: windows-driver-content
description: The FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET enumeration type specifies the data field identifiers for the FWPS_LAYER_INBOUND_MAC_FRAME_ETHERNET run-time filtering layer.
old-location: netvista\fwps_fields_inbound_mac_frame_802_3.htm
old-project: netvista
ms.assetid: 41313b4e-2f26-42a2-b3ec-d9b8c3041fac
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET_, FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 7
req.target-min-winversvr: Windows Server 2008 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET
req.alt-loc: fwpsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET_ enumeration



## -description
The <b>FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET</b> enumeration type specifies the data field identifiers for the
  FWPS_LAYER_INBOUND_MAC_FRAME_ETHERNET 
  <a href="netvista.run_time_filtering_layer_identifiers">run-time filtering layer</a>.
  <div class="alert"><b>Note</b>  In Windows 7 and Windows Server 2008 R2, the name of this enumeration was <b>FWPS_FIELDS_INBOUND_MAC_FRAME_802_3</b>.</div>
<div> </div>




## -syntax

````
typedef enum FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET_ { 
  FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_INTERFACE_MAC_ADDRESS,
  FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS,
  FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS,
  FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS_TYPE,
  FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS_TYPE,
  FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_ETHER_TYPE,
  FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_VLAN_ID,
  FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_INTERFACE,
  FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_INTERFACE_INDEX,
  FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_NDIS_PORT,
  FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_L2_FLAGS,
  FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAX
} FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET;
````


## -enum-fields

### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_INTERFACE_MAC_ADDRESS

The inbound MAC frame IEEE 802.3 interface  MAC address field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS

The inbound MAC frame IEEE 802.3 local MAC address field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS

The inbound MAC frame IEEE 802.3 remote MAC address field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS_TYPE

The inbound MAC frame IEEE 802.3 local MAC address type field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS_TYPE

The inbound MAC frame IEEE 802.3 remote MAC address type field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_ETHER_TYPE

The inbound MAC frame  IEEE 802.3 EtherType field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_VLAN_ID

The inbound MAC frame IEEE 802.3 VLAN identifier field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_INTERFACE

The inbound MAC frame  IEEE 802.3 interface field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_INTERFACE_INDEX

The inbound MAC frame interface IEEE 802.3 interface index field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_NDIS_PORT

The inbound MAC frame IEEE 802.3 NDIS port field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_L2_FLAGS

The inbound MAC frame IEEE 802.3 flags field.


### -field FWPS_FIELD_INBOUND_MAC_FRAME_ETHERNET_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 7

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2008 R2

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fwpsk.h (include Fwpsk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.fwps_fields_outbound_mac_frame_802_3">FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

