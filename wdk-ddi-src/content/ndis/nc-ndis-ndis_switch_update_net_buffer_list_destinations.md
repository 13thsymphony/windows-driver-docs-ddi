---
UID: NC:ndis.NDIS_SWITCH_UPDATE_NET_BUFFER_LIST_DESTINATIONS
title: NDIS_SWITCH_UPDATE_NET_BUFFER_LIST_DESTINATIONS function
author: windows-driver-content
description: The Hyper-V extensible switch extension calls the UpdateNetBufferListDestinations function to commit modifications that the extension made to a packet that contains multiple extensible switch destination ports.
old-location: netvista\UpdateNetBufferListDestinations.htm
old-project: netvista
ms.assetid: 9A740524-0FC1-4585-8059-F678D4777F66
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NDIS_SWITCH_UPDATE_NET_BUFFER_LIST_DESTINATIONS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UpdateNetBufferListDestinations
req.alt-loc: Ndis.h
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
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# NDIS_SWITCH_UPDATE_NET_BUFFER_LIST_DESTINATIONS function



## -description

The Hyper-V extensible switch extension calls the <i>UpdateNetBufferListDestinations</i> function to commit modifications that the extension made to a packet that contains multiple extensible switch destination ports. The function saves these modifications to the out-of-band (OOB) extensible switch forwarding context of the packet's <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. 



The Hyper-V extensible switch extension calls the <i>UpdateNetBufferListDestinations</i> function to commit modifications that the extension made to a packet that contains multiple extensible switch destination ports. The function saves these modifications to the out-of-band (OOB) extensible switch forwarding context of the packet's <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. 



## -syntax

````
NDIS_SWITCH_UPDATE_NET_BUFFER_LIST_DESTINATIONS UpdateNetBufferListDestinations;

NDIS_STATUS UpdateNetBufferListDestinations(
  _In_    NDIS_SWITCH_CONTEXT                       NdisSwitchContext,
  _Inout_ PNET_BUFFER_LIST                          NetBufferList,
  _In_    UINT32                                    NumberOfNewDestinations,
  _In_    PNDIS_SWITCH_FORWARDING_DESTINATION_ARRAY Destinations
)
{ ... }
````


## -parameters

### -param NdisSwitchContext [in]

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.


### -param NetBufferList [in, out]

A pointer to a <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure for a single packet.

<div class="alert"><b>Note</b>  This structure must contain  an extensible switch forwarding context. If the extension created or cloned the  packet, it must have previously allocated this structure by calling the <a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a> function.</div>
<div> </div>

### -param NumberOfNewDestinations [in]

A UINT32 value that specifies the number of new destination ports that were added to the packet.


### -param Destinations [in]

A pointer to an <a href="..\ndis\ns-ndis-_ndis_switch_forwarding_destination_array.md">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure. This structure specifies the extensible switch destination ports of the packet.

<div class="alert"><b>Note</b>  The extension received this structure through a previous call to the <a href="https://msdn.microsoft.com/55B5C0B4-5359-410B-9110-79EDDBA3010C">GetNetBufferListDestinations</a> function.</div>
<div> </div>

## -returns
If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.




## -remarks
The extensible switch extension calls the <a href="https://msdn.microsoft.com/55B5C0B4-5359-410B-9110-79EDDBA3010C">GetNetBufferListDestinations</a> function to obtain an array of the extensible switch destination ports for a packet. If the function returns successfully, the array is obtained through the <i>Destinations</i> parameter, which contains a pointer to a <a href="..\ndis\ns-ndis-_ndis_switch_forwarding_destination_array.md">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure. Each element in this array is formatted as an <a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a> structure that specifies a destination port for the packet.

After the extension obtains the <a href="..\ndis\ns-ndis-_ndis_switch_forwarding_destination_array.md">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure, the extension can do the following:

Add additional <a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a> elements in the array.

For more information, see <a href="https://msdn.microsoft.com/C921D9F8-B6FB-4B53-8CC5-CC941720FF37">Adding Extensible Switch Destination Port Data to a Packet</a>.

Modify existing <a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a> elements of the array to exclude a packet from being forwarded to a specified port.

For more information, see <a href="https://msdn.microsoft.com/04BF02A6-360F-482E-A86B-31232AFCB778">Excluding Packet Delivery to Extensible Switch Destination Ports</a>.

If the extension adds or modifies destination ports in the <a href="..\ndis\ns-ndis-_ndis_switch_forwarding_destination_array.md">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure, the extension must call the <i>UpdateNetBufferListDestinations</i> function to commit those changes to the packet's <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.

If the call to <i>UpdateNetBufferListDestinations</i> returns NDIS_STATUS_SUCCESS, the extensible switch interface guarantees that the extensible switch port and network adapter connection that are referenced in the destination ports will not be deleted until the packet's send or receive operation is completed. 

Also, after the changes for destination ports have been committed, destination ports cannot be removed, and only the <b>IsExcluded</b>  member of a destination port's <a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a> structure can be changed. For more information, see <a href="https://msdn.microsoft.com/04BF02A6-360F-482E-A86B-31232AFCB778">Excluding Packet Delivery to Extensible Switch Destination Ports</a>.

For more information about the extensible switch forwarding context, see <a href="https://msdn.microsoft.com/B2BF07B5-FA44-4994-9605-EFF4A0B9179F">Hyper-V Extensible Switch Forwarding Context</a>.


## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/55B5C0B4-5359-410B-9110-79EDDBA3010C">GetNetBufferListDestinations</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfoidrequest.md">NdisFOidRequest</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598264">OID_SWITCH_NIC_DELETE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_UPDATE_NET_BUFFER_LIST_DESTINATIONS callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

