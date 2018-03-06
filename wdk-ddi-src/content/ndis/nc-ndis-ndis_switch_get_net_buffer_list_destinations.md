---
UID: NC:ndis.NDIS_SWITCH_GET_NET_BUFFER_LIST_DESTINATIONS
title: NDIS_SWITCH_GET_NET_BUFFER_LIST_DESTINATIONS
author: windows-driver-content
description: The GetNetBufferListDestinations function returns the Hyper-V extensible switch destination ports of a packet that is specified by a NET_BUFFER_LIST structure.
old-location: netvista\GetNetBufferListDestinations.htm
old-project: netvista
ms.assetid: 55B5C0B4-5359-410B-9110-79EDDBA3010C
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetNetBufferListDestinations, GetNetBufferListDestinations callback function [Network Drivers Starting with Windows Vista], NDIS_SWITCH_GET_NET_BUFFER_LIST_DESTINATIONS, ndis/GetNetBufferListDestinations, netvista.GetNetBufferListDestinations
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	GetNetBufferListDestinations
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---


# NDIS_SWITCH_GET_NET_BUFFER_LIST_DESTINATIONS callback function
The <i>GetNetBufferListDestinations</i> function returns the Hyper-V extensible switch destination ports of a packet that is specified by a <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.

## Syntax

```
NDIS_SWITCH_GET_NET_BUFFER_LIST_DESTINATIONS NdisSwitchGetNetBufferListDestinations;

void NdisSwitchGetNetBufferListDestinations(
  NDIS_SWITCH_CONTEXT NdisSwitchContext,
  PNET_BUFFER_LIST NetBufferList,
  PNDIS_SWITCH_FORWARDING_DESTINATION_ARRAY * Destinations
)
{...}
```

## Parameters

`NdisSwitchContext`

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.

`NetBufferList`

A pointer to a linked list of <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures.  

<div class="alert"><b>Note</b>  If the <i>NetBufferList</i> parameter contains a pointer to a linked-list of multiple <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures, the destination ports are only returned from the first  <b>NET_BUFFER_LIST</b> structure in the list.</div>
<div> </div>

`Destinations`

A pointer to an <a href="..\ndis\ns-ndis-_ndis_switch_forwarding_destination_array.md">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure. This structure specifies the extensible switch destination ports of the packet.


## Return Value

If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.

## Remarks

The extensible switch extension calls the <i>GetNetBufferListDestinations</i> function to obtain an array of the extensible switch destination ports for a packet. If the function returns successfully, the array is obtained through the <i>Destinations</i> parameter, which contains a pointer to an <a href="..\ndis\ns-ndis-_ndis_switch_forwarding_destination_array.md">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure. Each element in this array is formatted as an <a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a> structure that specifies a destination port for the packet.

If the extension is allocating a packet, the extension must first call the <a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a> function before it calls <i>GetNetBufferListDestinations</i>. The <i>AllocateNetBufferListForwardingContext</i> function allocates the extensible switch forwarding context for the packet. This context contains the out-of-band (OOB) extensible switch data that includes the <a href="..\ndis\ns-ndis-_ndis_switch_forwarding_destination_array.md">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure. 

For more information about the extensible switch forwarding context, see <a href="https://msdn.microsoft.com/B2BF07B5-FA44-4994-9605-EFF4A0B9179F">Hyper-V Extensible Switch Forwarding Context</a>.

After the extension has obtained the array, it can do the following:

<ul>
<li>
Allocate space for additional <a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a> elements in the array. 

For more information, see <a href="https://msdn.microsoft.com/C921D9F8-B6FB-4B53-8CC5-CC941720FF37">Adding Extensible Switch Destination Port Data to a Packet</a>.

</li>
<li>
Modify the destination port information in the <a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a> elements of the array. For example, the extension can specify which port the packet is to be forwarded to or can exclude a packet from being forwarded to a specified port.

For more information, see <a href="https://msdn.microsoft.com/44338441-160C-4CD1-8C0B-27CFBE136910">Modifying a Packet's Extensible Switch Source Port Data</a>.

</li>
</ul>
<div class="alert"><b>Note</b>  The <a href="..\ndis\ns-ndis-_ndis_switch_forwarding_destination_array.md">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure is guaranteed to be valid while the extension retains ownership of the packet's <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.</div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.30 and later.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\ndis\ns-ndis-_ndis_switch_forwarding_destination_array.md">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a>



<a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



<a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a>



<a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_GET_NET_BUFFER_LIST_DESTINATIONS callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>