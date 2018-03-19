---
UID: NS:ndischimney._NEIGHBOR_OFFLOAD_STATE_DELEGATED
title: "_NEIGHBOR_OFFLOAD_STATE_DELEGATED"
author: windows-driver-content
description: The NEIGHBOR_OFFLOAD_STATE_DELGATED structure contains the delegated variable of a neighbor state object.
old-location: netvista\neighbor_offload_state_delegated.htm
old-project: netvista
ms.assetid: 94a35d0f-3585-45d0-bba8-0b4a8ebbe883
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNEIGHBOR_OFFLOAD_STATE_DELEGATED, NEIGHBOR_OFFLOAD_STATE_DELEGATED, NEIGHBOR_OFFLOAD_STATE_DELEGATED structure [Network Drivers Starting with Windows Vista], PNEIGHBOR_OFFLOAD_STATE_DELEGATED, PNEIGHBOR_OFFLOAD_STATE_DELEGATED structure pointer [Network Drivers Starting with Windows Vista], _NEIGHBOR_OFFLOAD_STATE_DELEGATED, ndischimney/NEIGHBOR_OFFLOAD_STATE_DELEGATED, ndischimney/PNEIGHBOR_OFFLOAD_STATE_DELEGATED, netvista.neighbor_offload_state_delegated, tcp_chim_struct_860c3a42-4276-4a6e-92c2-c32bc1afa9b2.xml"
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
-	NEIGHBOR_OFFLOAD_STATE_DELEGATED
product: Windows
targetos: Windows
req.typenames: NEIGHBOR_OFFLOAD_STATE_DELEGATED, *PNEIGHBOR_OFFLOAD_STATE_DELEGATED
---

# _NEIGHBOR_OFFLOAD_STATE_DELEGATED structure
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NEIGHBOR_OFFLOAD_STATE_DELGATED structure contains the delegated variable of a neighbor state
  object.

## Syntax
````
typedef struct _NEIGHBOR_OFFLOAD_STATE_DELEGATED {
  OFFLOAD_STATE_HEADER Header;
  ULONG                NicReachabilityDelta;
} NEIGHBOR_OFFLOAD_STATE_DELEGATED, *PNEIGHBOR_OFFLOAD_STATE_DELEGATED;
````

## Members


`Header`

An 
     <a href="..\ndischimney\ns-ndischimney-_offload_state_header.md">OFFLOAD_STATE_HEADER</a> structure. NDIS
     sets the 
     <b>Length</b> member of 
     <b>Header</b> to the size, in bytes, of the NEIGHBOR_OFFLOAD_STATE_DELEGATED structure. The 
     <b>RecognizedOptions</b> member of 
     <b>Header</b> is reserved.

`NicReachabilityDelta`

The NIC's current time minus the 
     <b>NicReachabilityDelta</b> is the last time that the offload target confirmed neighbor reachability (see
     forward reachability in RFC 2461). For information about how the offload target uses this variable, see 
     <a href="..\ndischimney\nf-ndischimney-ndismoffloadeventindicate.md">NdisMOffloadEventIndicate</a>. 
     <b>NicReachabilityDelta</b> is measured in units of clock ticks.

## Remarks
The host stack provides initial values for the 
    <b>NicReachabilityDelta</b> variable when it offloads the variable to the offload target. After it's been
    offloaded, the 
    <b>NicReachabilityDelta</b> variable is owned and maintained by the offload target. Only the offload
    target can change the value of an offloaded 
    <b>NicReachabilityDelta</b> variable. The offload target does not notify the host stack of changes to the
    values of an offloaded 
    <b>NicReachabilityDelta</b> variable. However, the host stack can query the value of an offloaded 
    <b>NicReachabilityDelta</b> variable, which causes NDIS to call the offload target's 
    <a href="..\ndischimney\nc-ndischimney-w_query_offload_handler.md">MiniportQueryOffload</a> function.
    When the host stack terminates the offload of a neighbor state object by causing NDIS to call the offload
    target's 
    <a href="..\ndischimney\nc-ndischimney-w_terminate_offload_handler.md">
    MiniportTerminateOffload</a> function, the offload target passes the value of the 
    <b>NicReachabilityDelta</b> variable in the terminated state object back to the host stack.

When passed to an offload target, a NEIGHBOR_OFFLOAD_STATE_DELEGATED structure is associated with an 
    <a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure, which contains a header that is formatted as an 
    <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure. The 
    <b>Revision</b> member of the NDIS_OBJECT_HEADER structure, in this case, specifies the revision number of
    the NEIGHBOR_OFFLOAD_STATE_DELEGATED structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ndischimney.h (include Ndischimney.h) |

## See Also

<a href="..\ndischimney\nc-ndischimney-w_query_offload_handler.md">MiniportQueryOffload</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndischimney\ns-ndischimney-_neighbor_offload_state_const.md">NEIGHBOR_OFFLOAD_STATE_CONST</a>



<a href="..\ndischimney\ns-ndischimney-_neighbor_offload_state_cached.md">NEIGHBOR_OFFLOAD_STATE_CACHED</a>



<a href="..\ndischimney\ns-ndischimney-_offload_state_header.md">OFFLOAD_STATE_HEADER</a>



<a href="..\ndischimney\nc-ndischimney-w_terminate_offload_handler.md">MiniportTerminateOffload</a>