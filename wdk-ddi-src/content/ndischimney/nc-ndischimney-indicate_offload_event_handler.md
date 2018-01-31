---
UID : NC:ndischimney.INDICATE_OFFLOAD_EVENT_HANDLER
title : INDICATE_OFFLOAD_EVENT_HANDLER
author : windows-driver-content
description : NDIS calls a protocol driver's or intermediate driver's ProtocolIndicateOffloadEvent function to post an indication that was initiated by an underlying driver's or offload target's call to the NdisMOffloadEventIndicate function.
old-location : netvista\protocolindicateoffloadevent.htm
old-project : netvista
ms.assetid : 608c1c7c-1eb3-4d86-9471-313fce2df00e
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.protocolindicateoffloadevent, ProtocolIndicateOffloadEvent callback function [Network Drivers Starting with Windows Vista], ProtocolIndicateOffloadEvent, INDICATE_OFFLOAD_EVENT_HANDLER, INDICATE_OFFLOAD_EVENT_HANDLER, ndischimney/ProtocolIndicateOffloadEvent, tcp_chim_protocol_func_cc94798f-b74a-45d5-b78f-383698003486.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : ndischimney.h
req.include-header : Ndischimney.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PD_BUFFER_VIRTUAL_SUBNET_INFO
---


# INDICATE_OFFLOAD_EVENT_HANDLER callback function
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol driver's or intermediate driver's 
  <i>ProtocolIndicateOffloadEvent</i> function to post an indication that was initiated by an underlying
  driver's or offload target's call to the 
  <mshelp:link keywords="netvista.ndismoffloadeventindicate" tabindex="0"><b>
  NdisMOffloadEventIndicate</b></mshelp:link> function.

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
     <mshelp:link keywords="netvista.ndis_protocol_offload_block_list" tabindex="0"><b>
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</b></mshelp:link> structure. This structure identifies the offloaded state object
     on which the indication is being made. Note that there is only one NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
     structure. There is not a linked list of such structures. 
     

The underlying offload target supplies a valid 
     <i>OffloadBlockList</i> pointer when making a 
     <b>NeighborReachabilityQuery</b> indication. In this case, the offload target supplies a 
     <mshelp:link keywords="netvista.neighbor_offload_state_const" tabindex="0"><b>
     NEIGHBOR_OFFLOAD_STATE_CONST</b></mshelp:link> structure, a 
     <mshelp:link keywords="netvista.neighbor_offload_state_cached" tabindex="0"><b>
     NEIGHBOR_OFFLOAD_STATE_CACHED</b></mshelp:link> structure, and a 
     <mshelp:link keywords="netvista.neighbor_offload_state_delegated" tabindex="0"><b>
     NEIGHBOR_OFFLOAD_STATE_DELEGATED</b></mshelp:link> structure (in that order) immediately following the
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
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndischimney.h (include Ndischimney.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\ndischimney\ns-ndischimney-_neighbor_offload_state_cached.md">NEIGHBOR_OFFLOAD_STATE_CACHED</a>

<mshelp:link keywords="netvista.neighbor_offload_state_delegated" tabindex="0"><b>
   NEIGHBOR_OFFLOAD_STATE_DELEGATED</b></mshelp:link>

<a href="..\ndischimney\ns-ndischimney-_neighbor_offload_state_const.md">NEIGHBOR_OFFLOAD_STATE_CONST</a>

<mshelp:link keywords="netvista.ndis_protocol_offload_block_list" tabindex="0"><b>
   NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</b></mshelp:link>

<a href="..\ndischimney\nf-ndischimney-ndismoffloadeventindicate.md">NdisMOffloadEventIndicate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20INDICATE_OFFLOAD_EVENT_HANDLER callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>