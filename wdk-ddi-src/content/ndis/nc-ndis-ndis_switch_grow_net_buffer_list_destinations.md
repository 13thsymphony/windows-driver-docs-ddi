---
UID: NC:ndis.NDIS_SWITCH_GROW_NET_BUFFER_LIST_DESTINATIONS
title: NDIS_SWITCH_GROW_NET_BUFFER_LIST_DESTINATIONS
author: windows-driver-content
description: The GrowNetBufferListDestinations function adds space for additional Hyper-V extensible switch destination ports to a packet that is specified by a NET_BUFFER_LIST structure.
old-location: netvista\grownetbufferlistdestinations.htm
old-project: netvista
ms.assetid: 9A79F41F-566F-4844-BF1A-E8889E6FDCE8
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GrowNetBufferListDestinations, GrowNetBufferListDestinations callback function [Network Drivers Starting with Windows Vista], NDIS_SWITCH_GROW_NET_BUFFER_LIST_DESTINATIONS, ndis/GrowNetBufferListDestinations, netvista.grownetbufferlistdestinations
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
-	GrowNetBufferListDestinations
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---


# NDIS_SWITCH_GROW_NET_BUFFER_LIST_DESTINATIONS callback function
The <i>GrowNetBufferListDestinations</i> function adds space for additional Hyper-V extensible switch destination ports to a packet that is specified by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.

## Syntax

```
NDIS_SWITCH_GROW_NET_BUFFER_LIST_DESTINATIONS NdisSwitchGrowNetBufferListDestinations;

NDIS_STATUS NdisSwitchGrowNetBufferListDestinations(
  NDIS_SWITCH_CONTEXT NdisSwitchContext,
  PNET_BUFFER_LIST NetBufferList,
  UINT32 NumberOfNewDestinations,
  PNDIS_SWITCH_FORWARDING_DESTINATION_ARRAY *Destinations
)
{...}
```

## Parameters

`NdisSwitchContext`

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="https://msdn.microsoft.com/library/windows/hardware/hh598204">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.

`NetBufferList`



`NumberOfNewDestinations`

A UINT32 value that specifies the number of new destination ports to be  added for the packet.

`Destinations`

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh598210">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure. This structure specifies the extensible switch destination ports of the packet.


## Return Value

If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.

## Remarks

The extensible switch extension calls the <i>GrowNetBufferListDestinations</i> function to add space for destination ports for a packet. Port destinations are specified through an <a href="https://msdn.microsoft.com/library/windows/hardware/hh598210">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a> structure.

For more information on how to add destination ports to a packet, see <a href="https://msdn.microsoft.com/C921D9F8-B6FB-4B53-8CC5-CC941720FF37">Adding Extensible Switch Destination Port Data to a Packet</a>.

<div class="alert"><b>Note</b>  If the <i>NetBufferList</i> parameter contains a pointer to a linked-list of multiple <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures, space for additional destination ports is only added to the first  <b>NET_BUFFER_LIST</b> structure in the list.</div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.30 and later.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<b></b>



<a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598210">NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598224">NDIS_SWITCH_PORT_DESTINATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598204">NdisFGetOptionalSwitchHandlers</a>



<a href="https://msdn.microsoft.com/9A740524-0FC1-4585-8059-F678D4777F66">UpdateNetBufferListDestinations</a>