---
UID: NS.NDIS._NET_DEVICE_PNP_EVENT
title: _NET_DEVICE_PNP_EVENT
author: windows-driver-content
description: The NET_DEVICE_PNP_EVENT structure defines device plug and play (PnP) events for miniport adapters.
old-location: netvista\net_device_pnp_event.htm
old-project: netvista
ms.assetid: 79298332-2d34-4ef3-ad43-5d218e3f6612
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _NET_DEVICE_PNP_EVENT, NET_DEVICE_PNP_EVENT, *PNET_DEVICE_PNP_EVENT
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
req.alt-api: NET_DEVICE_PNP_EVENT
req.alt-loc: ndis.h
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
---

# _NET_DEVICE_PNP_EVENT structure



## -description
The <b>NET_DEVICE_PNP_EVENT</b> structure defines device plug and play (PnP) events for miniport
  adapters.



## -syntax

````
typedef struct _NET_DEVICE_PNP_EVENT {
  NDIS_OBJECT_HEADER    Header;
  NDIS_PORT_NUMBER      PortNumber;
  NDIS_DEVICE_PNP_EVENT DevicePnPEvent;
  PVOID                 InformationBuffer;
  ULONG                 InformationBufferLength;
  UCHAR                 NdisReserved[2 * sizeof(PVOID)];
} NET_DEVICE_PNP_EVENT, *PNET_DEVICE_PNP_EVENT;
````


## -struct-fields

### -field Header

The 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     <b>NET_DEVICE_PNP_EVENT</b> structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_DEFAULT</b>, the 
     <b>Revision</b> member to <b>NET_DEVICE_PNP_EVENT_REVISION_1</b>, and the 
     <b>Size</b> member to <b>NDIS_SIZEOF_NET_DEVICE_PNP_EVENT_REVISION_1</b>.


### -field PortNumber

The source port of the PnP event notification. If the status indication is not specific to a port,
     
     <b>PortNumber</b> is zero.


### -field DevicePnPEvent

An event code that describes the PnP event as one of the following: 
     




### -field NdisDevicePnPEventSurpriseRemoved

The network interface card (NIC) has been unexpectedly removed from the
       computer. For more information, see <a href="netvista.handling_the_surprise_removal_of_a_nic">Handling the Surprise Removal of a NIC</a>.


### -field NdisDevicePnPEventPowerProfileChanged

The power profile of the host system has changed.

</dd>
</dl>

### -field InformationBuffer

A pointer to a buffer. If NDIS sets the 
     <b>DevicePnPEvent</b> member to 
     <b>NdisDevicePnPEventPowerProfileChanged</b>, this buffer will contain a ULONG that NDIS sets to one of
     the following values:
     




### -field NdisPowerProfileBattery

The host system is running on battery power.


### -field NdisPowerProfileAcOnline

The host system is running on AC power.

</dd>
</dl>
If NDIS sets 
     <b>DevicePnPEvent</b> to 
     <b>NdisDevicePnPEventSurpriseRemoved</b>, 
     <b>InformationBuffer</b> is <b>NULL</b>.


### -field InformationBufferLength

The length, in bytes, of the buffer in the 
     <b>InformationBuffer</b> member.


### -field NdisReserved

Reserved for NDIS.


## -remarks
To provide a device PnP event notification, NDIS passes a pointer to a <b>NET_DEVICE_PNP_EVENT</b> structure
    to the 
    <a href="..\ndis\nc-ndis-miniport_device_pnp_event_notify.md">
    MiniportDevicePnPEventNotify</a> or 
    <a href="..\ndis\nc-ndis-filter_device_pnp_event_notify.md">
    FilterDevicePnPEventNotify</a> function.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-filter_device_pnp_event_notify.md">FilterDevicePnPEventNotify</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_device_pnp_event_notify.md">
   MiniportDevicePnPEventNotify</a>
</dt>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NET_DEVICE_PNP_EVENT structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

