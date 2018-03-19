---
UID: NC:ndischimney.INDICATE_OFFLOAD_EVENT_HANDLER
title: INDICATE_OFFLOAD_EVENT_HANDLER
author: windows-driver-content
description: NDIS calls a protocol driver's or intermediate driver's ProtocolIndicateOffloadEvent function to post an indication that was initiated by an underlying driver's or offload target's call to the NdisMOffloadEventIndicate function.
old-location: netvista\protocolindicateoffloadevent.htm
old-project: netvista
ms.assetid: 608c1c7c-1eb3-4d86-9471-313fce2df00e
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: INDICATE_OFFLOAD_EVENT_HANDLER, ProtocolIndicateOffloadEvent, ProtocolIndicateOffloadEvent callback function [Network Drivers Starting with Windows Vista], ndischimney/ProtocolIndicateOffloadEvent, netvista.protocolindicateoffloadevent, tcp_chim_protocol_func_cc94798f-b74a-45d5-b78f-383698003486.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	UserDefined
api_location:
-	Ndischimney.h
api_name:
-	ProtocolIndicateOffloadEvent
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---


# INDICATE_OFFLOAD_EVENT_HANDLER callback function
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol driver's or intermediate driver's 
  <i>ProtocolIndicateOffloadEvent</i> function to post an indication that was initiated by an underlying
  driver's or offload target's call to the 
  <a href="..\ndischimney\nf-ndischimney-ndismoffloadeventindicate.md">
  NdisMOffloadEventIndicate</a> function.

## Syntax

```
INDICATE_OFFLOAD_EVENT_HANDLER IndicateOffloadEventHandler;

void IndicateOffloadEventHandler(
  IN NDIS_HANDLE ProtocolBindingContext,
  IN PNDIS_PROTOCOL_OFFLOAD_BLOCK_LIST OffloadBlockList,
  IN ULONG IndicationCode
)
{...}
```

## Parameters

`ProtocolBindingContext`

A handle to a context area that was allocated by the protocol driver. The driver maintains the per
     binding context information in this context area. The driver supplied this handle to NDIS when the
     driver called the 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function.

`OffloadBlockList`

A pointer to an 
     <a href="..\ndischimney\ns-ndischimney-_ndis_protocol_offload_block_list.md">
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a> structure. This structure identifies the offloaded state object
     on which the indication is being made. Note that there is only one NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
     structure. There is not a linked list of such structures. 
     

The underlying offload target supplies a valid 
     <i>OffloadBlockList</i> pointer when making a 
     <b>NeighborReachabilityQuery</b> indication. In this case, the offload target supplies a 
     <a href="..\ndischimney\ns-ndischimney-_neighbor_offload_state_const.md">
     NEIGHBOR_OFFLOAD_STATE_CONST</a> structure, a 
     <a href="..\ndischimney\ns-ndischimney-_neighbor_offload_state_cached.md">
     NEIGHBOR_OFFLOAD_STATE_CACHED</a> structure, and a 
     <a href="..\ndischimney\ns-ndischimney-_neighbor_offload_state_delegated.md">
     NEIGHBOR_OFFLOAD_STATE_DELEGATED</a> structure (in that order) immediately following the
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure referenced by the 
     <i>OffloadBlockList</i> pointer.

`IndicationCode`

The event being indicated as one of the following INDICATE_OFFLOAD_EVENT values:
     





#### NeighborReachabilityQuery

Indicates that a neighbor cache entry (NCE) has become stale. For more information about NCEs,
       see RFC 2461.



#### NeighborReachabilityInDoubt

Reserved.


## Return Value

None

## Remarks

The implementation of this function for intermediate drivers is to be determined.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ndischimney.h (include Ndischimney.h) |

## See Also

<a href="..\ndischimney\ns-ndischimney-_neighbor_offload_state_delegated.md">
   NEIGHBOR_OFFLOAD_STATE_DELEGATED</a>



<a href="..\ndischimney\ns-ndischimney-_neighbor_offload_state_const.md">NEIGHBOR_OFFLOAD_STATE_CONST</a>



<a href="..\ndischimney\ns-ndischimney-_neighbor_offload_state_cached.md">NEIGHBOR_OFFLOAD_STATE_CACHED</a>



<a href="..\ndischimney\nf-ndischimney-ndismoffloadeventindicate.md">NdisMOffloadEventIndicate</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_protocol_offload_block_list.md">
   NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a>