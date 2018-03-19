---
UID: NE:fwpsk.FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET_
title: FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET_
author: windows-driver-content
description: The FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET enumeration type specifies the data field identifiers for the FWPS_LAYER_OUTBOUND_MAC_FRAME_ETHERNET run-time filtering layer.
old-location: netvista\fwps_fields_outbound_mac_frame_802_3.htm
old-project: netvista
ms.assetid: 954dc1a8-006f-4a78-bc7a-1fef4d7b4186
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET, FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET_, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_ETHER_TYPE, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_FLAGS, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_INTERFACE, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_INTERFACE_INDEX, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_INTERFACE_MAC_ADDRESS, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS_TYPE, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS_TYPE, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAX, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_NDIS_PORT, FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_VLAN_ID, fwpsk/FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_ETHER_TYPE, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_FLAGS, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_INTERFACE, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_INTERFACE_INDEX, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_INTERFACE_MAC_ADDRESS, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS_TYPE, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS_TYPE, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAX, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_NDIS_PORT, fwpsk/FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_VLAN_ID, netvista.fwps_fields_outbound_mac_frame_802_3, wfp_ref_5_const_3_data_fields_d53ec059-3f9a-4eef-9994-94e6923145aa.xml
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fwpsk.h
api_name:
-	FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET
product: Windows
targetos: Windows
req.typenames: FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET
---

# FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET_ Enumeration
The <b>FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET</b> enumeration type specifies the data field identifiers for the
  FWPS_LAYER_OUTBOUND_MAC_FRAME_ETHERNET 
  <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa366492">run-time filtering layer</a>.
  <div class="alert"><b>Note</b>  In Windows 7 and Windows Server 2008 R2, the name of this enumeration was <b>FWPS_FIELDS_OUTBOUND_MAC_FRAME_802_3</b>.</div>
<div> </div>

## Syntax
````
typedef enum FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET_ { 
  FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_INTERFACE_MAC_ADDRESS,
  FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS,
  FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS,
  FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS_TYPE,
  FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS_TYPE,
  FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_ETHER_TYPE,
  FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_VLAN_ID,
  FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_INTERFACE,
  FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_INTERFACE_INDEX,
  FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_NDIS_PORT,
  FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_FLAGS,
  FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAX
} FWPS_FIELDS_OUTBOUND_MAC_FRAME_ETHERNET;
````

## Constants

<table>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_INTERFACE_MAC_ADDRESS</td>
                    <td>The outbound MAC frame IEEE 802.3 interface MAC address field.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS</td>
                    <td>The outbound MAC frame IEEE 802.3 local MAC address field.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS</td>
                    <td>The outbound MAC frame IEEE 802.3 remote MAC address field.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_LOCAL_ADDRESS_TYPE</td>
                    <td>The outbound MAC frame IEEE 802.3 local MAC address type field.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAC_REMOTE_ADDRESS_TYPE</td>
                    <td>The outbound MAC frame IEEE 802.3 remote MAC address type field.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_ETHER_TYPE</td>
                    <td>The outbound MAC frame IEEE 802.3 EtherType field.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_VLAN_ID</td>
                    <td>The outbound MAC frame IEEE 802.3  VLAN   identifier field.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_INTERFACE</td>
                    <td>The outbound MAC frame IEEE 802.3 interface field.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_INTERFACE_INDEX</td>
                    <td>The outbound MAC frame IEEE 802.3 interface index field.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_NDIS_PORT</td>
                    <td>The outbound MAC frame IEEE 802.3 NDIS port field.</td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_L2_FLAGS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_COMPARTMENT_ID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>FWPS_FIELD_OUTBOUND_MAC_FRAME_ETHERNET_MAX</td>
                    <td>The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 7 Windows 7 |
| **Header** | fwpsk.h (include Fwpsk.h) |

## See Also

<a href="..\fwpsk\ne-fwpsk-fwps_fields_inbound_mac_frame_ethernet_.md">FWPS_FIELDS_INBOUND_MAC_FRAME_ETHERNET</a>