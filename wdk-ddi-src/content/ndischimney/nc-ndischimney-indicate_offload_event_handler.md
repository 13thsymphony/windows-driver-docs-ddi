---
UID: NC.ndischimney.INDICATE_OFFLOAD_EVENT_HANDLER
title: INDICATE_OFFLOAD_EVENT_HANDLER
author: windows-driver-content
description: NDIS calls a protocol driver's or intermediate driver's ProtocolIndicateOffloadEvent function to post an indication that was initiated by an underlying driver's or offload target's call to the NdisMOffloadEventIndicate function.
old-location: netvista\protocolindicateoffloadevent.htm
old-project: netvista
ms.assetid: 608c1c7c-1eb3-4d86-9471-313fce2df00e
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _PD_BUFFER_VIRTUAL_SUBNET_INFO, PD_BUFFER_VIRTUAL_SUBNET_INFO
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
req.alt-api: ProtocolIndicateOffloadEvent
req.alt-loc: Ndischimney.h
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
---

# INDICATE_OFFLOAD_EVENT_HANDLER callback



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol driver's or intermediate driver's 
  <i>ProtocolIndicateOffloadEvent</i> function to post an indication that was initiated by an underlying
  driver's or offload target's call to the 
  <a href="netvista.ndismoffloadeventindicate">
  NdisMOffloadEventIndicate</a> function.



## -prototype

````
INDICATE_OFFLOAD_EVENT_HANDLER ProtocolIndicateOffloadEvent;

VOID ProtocolIndicateOffloadEvent(
  _In_ NDIS_HANDLE                       ProtocolBindingContext,
  _In_ PNDIS_PROTOCOL_OFFLOAD_BLOCK_LIST OffloadBlockList,
  _In_ ULONG                             IndicationCode
)
{ ... }
````


## -parameters

### -param ProtocolBindingContext [in]

A handle to a context area that was allocated by the protocol driver. The driver maintains the per
     binding context information in this context area. The driver supplied this handle to NDIS when the
     driver called the 
     <a href="netvista.ndisopenadapterex">NdisOpenAdapterEx</a> function.


### -param OffloadBlockList [in]

A pointer to an 
     <a href="netvista.ndis_protocol_offload_block_list">
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a> structure. This structure identifies the offloaded state object
     on which the indication is being made. Note that there is only one NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
     structure. There is not a linked list of such structures. 
     

The underlying offload target supplies a valid 
     <i>OffloadBlockList</i> pointer when making a 
     <b>NeighborReachabilityQuery</b> indication. In this case, the offload target supplies a 
     <a href="netvista.neighbor_offload_state_const">
     NEIGHBOR_OFFLOAD_STATE_CONST</a> structure, a 
     <a href="netvista.neighbor_offload_state_cached">
     NEIGHBOR_OFFLOAD_STATE_CACHED</a> structure, and a 
     <a href="netvista.neighbor_offload_state_delegated">
     NEIGHBOR_OFFLOAD_STATE_DELEGATED</a> structure (in that order) immediately following the
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure referenced by the 
     <i>OffloadBlockList</i> pointer.


### -param IndicationCode [in]

The event being indicated as one of the following INDICATE_OFFLOAD_EVENT values:
     




### -param NeighborReachabilityQuery

Indicates that a neighbor cache entry (NCE) has become stale. For more information about NCEs,
       see RFC 2461.


### -param NeighborReachabilityInDoubt

Reserved.

</dd>
</dl>

## -returns
None


## -remarks
The implementation of this function for intermediate drivers is to be determined.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndischimney.h (include Ndischimney.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.neighbor_offload_state_cached">NEIGHBOR_OFFLOAD_STATE_CACHED</a>
</dt>
<dt>
<a href="netvista.neighbor_offload_state_const">NEIGHBOR_OFFLOAD_STATE_CONST</a>
</dt>
<dt>
<a href="netvista.neighbor_offload_state_delegated">
   NEIGHBOR_OFFLOAD_STATE_DELEGATED</a>
</dt>
<dt>
<a href="netvista.ndis_protocol_offload_block_list">
   NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a>
</dt>
<dt>
<a href="netvista.ndismoffloadeventindicate">NdisMOffloadEventIndicate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20INDICATE_OFFLOAD_EVENT_HANDLER callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

