---
UID: NS:ndis._NDIS_SWITCH_PORT_DESTINATION
title: "_NDIS_SWITCH_PORT_DESTINATION"
author: windows-driver-content
description: The NDIS_SWITCH_PORT_DESTINATION structure specifies the Hyper-V extensible switch destination port to which a packet will be delivered.
old-location: netvista\ndis_switch_port_destination.htm
old-project: netvista
ms.assetid: EC7FFB5E-F50B-40C4-B4B7-0A11A374EBD0
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_SWITCH_PORT_DESTINATION, NDIS_SWITCH_PORT_DESTINATION, NDIS_SWITCH_PORT_DESTINATION structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_PORT_DESTINATION, PNDIS_SWITCH_PORT_DESTINATION structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PORT_DESTINATION, ndis/NDIS_SWITCH_PORT_DESTINATION, ndis/PNDIS_SWITCH_PORT_DESTINATION, netvista.ndis_switch_port_destination"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ndis.h
api_name:
-	NDIS_SWITCH_PORT_DESTINATION
product:
- Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_DESTINATION, *PNDIS_SWITCH_PORT_DESTINATION
---

# _NDIS_SWITCH_PORT_DESTINATION structure
The <b>NDIS_SWITCH_PORT_DESTINATION</b> structure specifies the Hyper-V extensible switch destination port to which a packet will be delivered.

## Syntax
```
typedef struct _NDIS_SWITCH_PORT_DESTINATION {
  NDIS_SWITCH_PORT_ID   PortId;
  NDIS_SWITCH_NIC_INDEX NicIndex;
  USHORT  : 1           IsExcluded;
  USHORT  : 1           PreserveVLAN;
  USHORT  : 1           PreservePriority;
  USHORT  : 13          Reserved;
} NDIS_SWITCH_PORT_DESTINATION, *PNDIS_SWITCH_PORT_DESTINATION;
```

## Members


`PortId`

An NDIS_SWITCH_PORT_ID value that specifies the unique identifier of the destination port on the extensible switch.

`NicIndex`

An NDIS_SWITCH_NIC_INDEX value that specifies the index of the network adapter that is connected to the  extensible switch port specified by the <b>PortId</b> member.

For more information on NDIS_SWITCH_NIC_INDEX values, see <a href="https://msdn.microsoft.com/969333DA-0282-474B-8D56-72CD623C5329">Network Adapter Index Values</a>.

<div class="alert"><b>Note</b>  This member must specify the index value of a network adapter that is in a connected state. Index values for network adapters that are in a created or disconnected state cannot be specified. For more information about network connection states, see <a href="https://msdn.microsoft.com/1E2075E3-D7CC-4364-ABB2-D5969DB361B5">Hyper-V Extensible Switch Port and Network Adapter States</a>.</div>
<div> </div>

`IsExcluded`

If this member is set to TRUE, the packet will not be delivered to the
    destination port.

`PreserveVLAN`

If this member is set to TRUE, the 802.1Q virtual local area network (VLAN) information will be preserved when the packet is delivered to the destination port.

`PreservePriority`

If this member is set to TRUE, the 802.1Q priority information will be preserved when the packet is delivered to the destination port.

`Reserved`

This member is reserved for future use by NDIS.

## Remarks
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh598210">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> contains one or more elements. Each element is formatted as an <b>NDIS_SWITCH_PORT_DESTINATION</b> structure.

<div class="alert"><b>Note</b>  The <b>NicIndex</b> member must specify the index value of a network adapter that is in a connected state. Index values for network adapters that are in a created or disconnected state cannot be specified. For more information about network connection states, see <a href="https://msdn.microsoft.com/1E2075E3-D7CC-4364-ABB2-D5969DB361B5">Hyper-V Extensible Switch Port and Network Adapter States</a>.</div>
<div> </div>
For more information on destination ports, see <a href="https://msdn.microsoft.com/2781E64A-61D6-49A9-AD9B-F6B348560E30">Managing Hyper-V Extensible Switch Destination Port Data</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.30 and later. Supported in NDIS 6.30 and later. |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598210">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a>