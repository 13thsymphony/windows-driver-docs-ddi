---
UID: NC:ndis.NDIS_SWITCH_ADD_NET_BUFFER_LIST_DESTINATION
title: NDIS_SWITCH_ADD_NET_BUFFER_LIST_DESTINATION
author: windows-driver-content
description: The AddNetBufferListDestination function adds a single destination port for a packet that is specified by a NET_BUFFER_LIST structure.
old-location: netvista\AddNetBufferListDestination.htm
old-project: netvista
ms.assetid: 6B8CD868-D2F4-4892-BF6D-DFD7A3984320
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.AddNetBufferListDestination, AddNetBufferListDestination callback function [Network Drivers Starting with Windows Vista], AddNetBufferListDestination, NDIS_SWITCH_ADD_NET_BUFFER_LIST_DESTINATION, NDIS_SWITCH_ADD_NET_BUFFER_LIST_DESTINATION, ndis/AddNetBufferListDestination
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ndis.h
apiname:
-	AddNetBufferListDestination
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---


# NDIS_SWITCH_ADD_NET_BUFFER_LIST_DESTINATION function
The <i>AddNetBufferListDestination</i> function adds a single destination port for a packet that is specified by a <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.

## Syntax

```
NDIS_SWITCH_ADD_NET_BUFFER_LIST_DESTINATION NdisSwitchAddNetBufferListDestination;

NDIS_STATUS NdisSwitchAddNetBufferListDestination(
  NDIS_SWITCH_CONTEXT NdisSwitchContext,
  PNET_BUFFER_LIST NetBufferList,
  PNDIS_SWITCH_PORT_DESTINATION Destination
)
{...}
```

## Parameters

`NdisSwitchContext`

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.

`NetBufferList`

A pointer to a <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure for a packet. 

<div class="alert"><b>Note</b>  This structure must contain  an extensible switch forwarding context. If the extension created or cloned the  packet, it must have previously allocated this structure by calling the <a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a> function.</div>
<div> </div>

`Destination`

A pointer to an <a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a> structure. This structure specifies the destination extensible switch port that the packet will be forwarded to.


## Return Value

If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.

## Remarks

The forwarding extensible switch extension calls <i>AddNetBufferListDestination</i> to define a single extensible switch destination port for a packet. The extension specifies this port by initializing an   <a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a> structure. The extension sets the <i>Destination</i> parameter to a pointer to this structure. For more information on how to specify an extensible switch destination port, see <a href="https://msdn.microsoft.com/2781E64A-61D6-49A9-AD9B-F6B348560E30">Managing Hyper-V Extensible Switch Destination Port Data</a>.

<div class="alert"><b>Note</b>  For performance reasons, the extension should not call <i>AddNetBufferListDestination</i> packets with multiple destination ports.</div>
<div> </div>
The extension must follow these guidelines before it calls <i>AddNetBufferListDestination</i>:

<ul>
<li>
Only forwarding extensions can call <i>AddNetBufferListDestination</i> to add a destination port for a packet. For more information on this type of extension, see <a href="https://msdn.microsoft.com/7ABBB3F3-66F5-4651-8A5A-94940F3FD82D">Forwarding Extensions</a>.

</li>
<li>
If the forwarding extension is originating a packet with one destination port, the extension must first call the <a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a> function. This function allocates the extensible switch forwarding context for the packet. This data contains the extensible switch source and destination ports within the out-of-band (OOB) information for the packet.

For more information about this context, see <a href="https://msdn.microsoft.com/B2BF07B5-FA44-4994-9605-EFF4A0B9179F">Hyper-V Extensible Switch Forwarding Context</a>.

</li>
<li>
After the extension modifies the destination port information in the <a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a> structure, it calls <i>AddNetBufferListDestination</i> to commit the changes to the <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure for the packet.

<div class="alert"><b>Note</b>  For performance reasons, the extension should not call the <a href="https://msdn.microsoft.com/9A740524-0FC1-4585-8059-F678D4777F66">UpdateNetBufferListDestinations</a> function to commit the changes for the packet.
</div>
<div> </div>
</li>
</ul>
<div class="alert"><b>Note</b>  After the forwarding extension commits the changes for destination ports to the forwarding context, destination ports cannot be removed and only the <b>IsExcluded</b>  member of a destination port's <a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a> structure can be changed. For more information, see <a href="https://msdn.microsoft.com/04BF02A6-360F-482E-A86B-31232AFCB778">Excluding Packet Delivery to Extensible Switch Destination Ports</a>.</div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.30 and later.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/55B5C0B4-5359-410B-9110-79EDDBA3010C">GetNetBufferListDestinations</a>



<a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a>



<a href="..\ndis\ns-ndis-_ndis_switch_port_destination.md">NDIS_SWITCH_PORT_DESTINATION</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_ADD_NET_BUFFER_LIST_DESTINATION callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>