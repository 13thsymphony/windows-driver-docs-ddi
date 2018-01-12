---
UID: NE:fwpsk.FWPS_FIELDS_INGRESS_VSWITCH_ETHERNET_
title: FWPS_FIELDS_INGRESS_VSWITCH_ETHERNET_
author: windows-driver-content
description: The FWPS_FIELDS_INGRESS_VSWITCH_ETHERNET (formerly WPS_FIELDS_INGRESS_VSWITCH_802_3) enumeration type specifies the data field identifiers for the FWPS_LAYER_INGRESS_VSWITCH_ETHERNET run-time filtering layer.
old-location: netvista\fwps_fields_ingress_vswitch_802_3.htm
old-project: netvista
ms.assetid: ec206a59-33a1-4812-8290-4a2d417e4747
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: FWPS_FIELDS_INGRESS_VSWITCH_ETHERNET_, FWPS_FIELDS_INGRESS_VSWITCH_ETHERNET
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FWPS_FIELDS_INGRESS_VSWITCH_ETHERNET
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
req.typenames: FWPS_FIELDS_INGRESS_VSWITCH_ETHERNET
---

# FWPS_FIELDS_INGRESS_VSWITCH_ETHERNET_ enumeration



## -description
The FWPS_FIELDS_INGRESS_VSWITCH_ETHERNET (formerly WPS_FIELDS_INGRESS_VSWITCH_802_3) enumeration type specifies the data field identifiers for the
  FWPS_LAYER_INGRESS_VSWITCH_ETHERNET 
  <a href="netvista.run_time_filtering_layer_identifiers">run-time filtering layer</a>.



## -syntax

````
typedef enum FWPS_FIELDS_INGRESS_VSWITCH_ETHERNET_ { 
  FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_MAC_SOURCE_ADDRESS,
  FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_MAC_SOURCE_ADDRESS_TYPE,
  FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_MAC_DESTINATION_ADDRESS,
  FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_MAC_DESTINATION_ADDRESS_TYPE,
  FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_ETHER_TYPE,
  FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_VLAN_ID,
  FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_TENANT_NETWORK_ID,
  FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_VSWITCH_ID,
  FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_VSWITCH_NETWORK_TYPE,
  FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_VSWITCH_SOURCE_INTERFACE_ID,
  FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_VSWITCH_SOURCE_INTERFACE_TYPE,
  FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_VSWITCH_SOURCE_VM_ID,
  FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_FLAGS,
  FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_MAX
} FWPS_FIELDS_INGRESS_VSWITCH_ETHERNET;
````


## -enum-fields

### -field FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_MAC_SOURCE_ADDRESS

The virtual switch ingress MAC source address field.


### -field FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_MAC_SOURCE_ADDRESS_TYPE

The virtual switch ingress MAC source address type field.


### -field FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_MAC_DESTINATION_ADDRESS

The virtual switch ingress MAC destination address field.


### -field FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_MAC_DESTINATION_ADDRESS_TYPE

The virtual switch ingress MAC destination address type field.


### -field FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_ETHER_TYPE

The virtual switch ingress Ethernet EtherType field.


### -field FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_VLAN_ID

The virtual switch ingress virtual  LAN (VLAN) identifier field.


### -field FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_TENANT_NETWORK_ID

The virtual switch ingress tenant network identifier   field.


### -field FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_VSWITCH_ID

The virtual switch ingress identifier field.


### -field FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_VSWITCH_NETWORK_TYPE

The virtual switch ingress network type field. 


### -field FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_VSWITCH_SOURCE_INTERFACE_ID

The virtual switch ingress source interface identifier field.


### -field FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_VSWITCH_SOURCE_INTERFACE_TYPE

The virtual switch ingress source interface type field.


### -field FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_VSWITCH_SOURCE_VM_ID

The virtual switch ingress source virtual machine (VM)  identifier field.


### -field FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_FLAGS

The virtual switch ingress ethernet flags field.


### -field FWPS_FIELD_INGRESS_VSWITCH_ETHERNET_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS header files and binaries.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with Windows 8.

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