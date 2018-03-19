---
UID: NS:ndischimney._NEIGHBOR_OFFLOAD_STATE_CACHED
title: "_NEIGHBOR_OFFLOAD_STATE_CACHED"
author: windows-driver-content
description: The NEIGHBOR_OFFLOAD_STATE_CACHED structure contains the cached variables of a neighbor state object.
old-location: netvista\neighbor_offload_state_cached.htm
old-project: netvista
ms.assetid: 5dedffa8-9745-4668-8646-0e896942b9c8
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNEIGHBOR_OFFLOAD_STATE_CACHED, NEIGHBOR_OFFLOAD_STATE_CACHED, NEIGHBOR_OFFLOAD_STATE_CACHED structure [Network Drivers Starting with Windows Vista], PNEIGHBOR_OFFLOAD_STATE_CACHED, PNEIGHBOR_OFFLOAD_STATE_CACHED structure pointer [Network Drivers Starting with Windows Vista], _NEIGHBOR_OFFLOAD_STATE_CACHED, ndischimney/NEIGHBOR_OFFLOAD_STATE_CACHED, ndischimney/PNEIGHBOR_OFFLOAD_STATE_CACHED, netvista.neighbor_offload_state_cached, tcp_chim_struct_053f9a79-057c-4d4b-8ad1-2910f0ad4a9a.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndischimney.h
api_name:
-	NEIGHBOR_OFFLOAD_STATE_CACHED
product: Windows
targetos: Windows
req.typenames: NEIGHBOR_OFFLOAD_STATE_CACHED, *PNEIGHBOR_OFFLOAD_STATE_CACHED
---

# _NEIGHBOR_OFFLOAD_STATE_CACHED structure
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NEIGHBOR_OFFLOAD_STATE_CACHED structure contains the cached variables of a neighbor state
  object.

## Syntax
````
typedef struct _NEIGHBOR_OFFLOAD_STATE_CACHED {
  OFFLOAD_STATE_HEADER Header;
  UCHAR                DlDestinationAddress[32];
  ULONG                HostReachabilityDelta;
} NEIGHBOR_OFFLOAD_STATE_CACHED, *PNEIGHBOR_OFFLOAD_STATE_CACHED;
````

## Members


`Header`

An 
     <a href="..\ndischimney\ns-ndischimney-_offload_state_header.md">OFFLOAD_STATE_HEADER</a> structure. NDIS
     sets the 
     <b>Length</b> member of 
     <b>Header</b> to the size, in bytes, of the NEIGHBOR_OFFLOAD_STATE_CACHED structure. The 
     <b>RecognizedOptions</b> member of 
     <b>Header</b> is reserved.

`DlDestinationAddress`

Specifies the media access control (MAC) address of the next hop (neighbor).

`HostReachabilityDelta`

The host stack's current time minus 
     <b>HostReachabilityDelta</b> is the last time that the host stack confirmed neighbor reachability (see
     forward reachability in RFC 2461). For information about how the offload target uses this variable, see 
     <a href="..\ndischimney\nf-ndischimney-ndismoffloadeventindicate.md">NdisMOffloadEventIndicate</a>. 
     <b>HostReachabilityDelta</b> is measured in units of clock ticks.

## Remarks
Cached variables are owned and maintained by the host stack. An offload target must not change the
    value of a cached variable unless requested to do so by the host stack. If the value of a cached variable
    changes, the host stack requests an update of the variable, which causes NDIS to call the offload
    target's 
    <a href="..\ndischimney\nc-ndischimney-w_update_offload_handler.md">MiniportUpdateOffload</a> function.
    When the host stack terminates the offload of one or more state objects by causing NDIS to call the
    offload target's 
    <a href="..\ndischimney\nc-ndischimney-w_terminate_offload_handler.md">
    MiniportTerminateOffload</a> function, the offload target does not return the value of offloaded
    constant variables to the host stack.

When passed to an offload target, a NEIGHBOR_OFFLOAD_STATE_CACHED structure is associated with an 
    <a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure, which contains a header that is formatted as an 
    <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure. The 
    <b>Revision</b> member of the NDIS_OBJECT_HEADER structure, in this case, specifies the revision number of
    the NEIGHBOR_OFFLOAD_STATE_CACHED structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ndischimney.h (include Ndischimney.h) |

## See Also

<a href="..\ndischimney\ns-ndischimney-_neighbor_offload_state_delegated.md">
   NEIGHBOR_OFFLOAD_STATE_DELEGATED</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndischimney\ns-ndischimney-_neighbor_offload_state_const.md">NEIGHBOR_OFFLOAD_STATE_CONST</a>



<a href="..\ndischimney\nc-ndischimney-w_update_offload_handler.md">MiniportUpdateOffload</a>



<a href="..\ndischimney\ns-ndischimney-_offload_state_header.md">OFFLOAD_STATE_HEADER</a>



<a href="..\ndischimney\nc-ndischimney-w_terminate_offload_handler.md">MiniportTerminateOffload</a>