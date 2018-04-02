---
UID: NS:ndis._NET_PNP_EVENT_NOTIFICATION
title: "_NET_PNP_EVENT_NOTIFICATION"
author: windows-driver-content
description: The NET_PNP_EVENT_NOTIFICATION structure describes a network Plug and Play (PnP) event, an NDIS PnP event, or a power management event.
old-location: netvista\net_pnp_event_notification.htm
old-project: netvista
ms.assetid: 58d3baf3-a1fa-42ae-b795-2774a148aeda
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNET_PNP_EVENT_NOTIFICATION, NET_PNP_EVENT_NOTIFICATION, NET_PNP_EVENT_NOTIFICATION structure [Network Drivers Starting with Windows Vista], PNET_PNP_EVENT_NOTIFICATION, PNET_PNP_EVENT_NOTIFICATION structure pointer [Network Drivers Starting with Windows Vista], _NET_PNP_EVENT_NOTIFICATION, ndis/NET_PNP_EVENT_NOTIFICATION, ndis/PNET_PNP_EVENT_NOTIFICATION, netvista.net_pnp_event_notification, protocol_structures_ref_48e5c834-8115-4a76-bf0d-bcbea8866d20.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
-	ndis.h
api_name:
-	NET_PNP_EVENT_NOTIFICATION
product: Windows
targetos: Windows
req.typenames: NET_PNP_EVENT_NOTIFICATION, *PNET_PNP_EVENT_NOTIFICATION
---

# _NET_PNP_EVENT_NOTIFICATION structure
The NET_PNP_EVENT_NOTIFICATION structure describes a network Plug and Play (PnP) event, an NDIS PnP
  event, or a power management event.

## Syntax
```
typedef struct _NET_PNP_EVENT_NOTIFICATION {
  NDIS_OBJECT_HEADER       Header;
  NDIS_PORT_NUMBER         PortNumber;
  NET_PNP_EVENT            NetPnPEvent;
  ULONG                    Flags;
  NDIS_NIC_SWITCH_ID       SwitchId;
  NDIS_NIC_SWITCH_VPORT_ID VPortId;
} NET_PNP_EVENT_NOTIFICATION, *PNET_PNP_EVENT_NOTIFICATION;
```

## Members


`Header`

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     NET_PNP_EVENT_NOTIFICATION structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NET_PNP_EVENT_NOTIFICATION_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_NET_PNP_EVENT_NOTIFICATION_REVISION_1.

`PortNumber`

The source port of the event notification. If the status indication is not specific to a port, 
     <b>PortNumber</b> is zero.

`NetPnPEvent`

A
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568751">NET_PNP_EVENT</a> structure that describes the
     event.

`Flags`



`SwitchId`



`VPortId`



## Remarks
When the operating system issues a system PnP event or a power management event to a target device
    object that represents an adapter, NDIS translates the event into a NET_PNP_EVENT_NOTIFICATION
    structure.

The 
    <b>NetPnPEvent</b> member is a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568751">NET_PNP_EVENT</a> structure. The 
    <b>NetEvent</b> member of this NET_PNP_EVENT structure specifies an event code that identifies the network
    PnP event, NDIS PnP event, or power management event.

The 
    <b>Buffer</b> member, which is in the NET_PNP_EVENT structure that is specified in the 
    <b>NetPnPEvent</b> member of NET_PNP_EVENT_NOTIFICATION, specifies the address of a buffer that contains
    information that is specific to the event that is indicated by the 
    <b>NetEvent</b> member.

NDIS also issues PnP event notifications for NDIS PnP events such as 
    <b>NetEventPause</b>, 
    <b>NetEventRestart</b>, 
    <b>NetEventPortActivation</b>, and 
    <b>NetEventPortDeactivation</b>.

NDIS passes a pointer to a NET_PNP_EVENT_NOTIFICATION structure to the 
    <a href="https://msdn.microsoft.com/5c52b2d2-3fba-4d28-8172-7b6854386061">FilterNetPnPEvent</a> function of
    overlying filter drivers and to the 
    <a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a> function of
    overlying protocol drivers.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later. Supported in NDIS 6.0 and later. |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/5c52b2d2-3fba-4d28-8172-7b6854386061">FilterNetPnPEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568751">NET_PNP_EVENT</a>



<a href="https://msdn.microsoft.com/3f50bcba-c7d2-4d81-bd8b-6080e08fbe74">ProtocolNetPnPEvent</a>