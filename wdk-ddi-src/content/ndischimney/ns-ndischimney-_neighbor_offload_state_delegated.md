---
UID: NS.NDISCHIMNEY._NEIGHBOR_OFFLOAD_STATE_DELEGATED
title: _NEIGHBOR_OFFLOAD_STATE_DELEGATED
author: windows-driver-content
description: The NEIGHBOR_OFFLOAD_STATE_DELGATED structure contains the delegated variable of a neighbor state object.
old-location: netvista\neighbor_offload_state_delegated.htm
old-project: NetVista
ms.assetid: 94a35d0f-3585-45d0-bba8-0b4a8ebbe883
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NEIGHBOR_OFFLOAD_STATE_DELEGATED, NEIGHBOR_OFFLOAD_STATE_DELEGATED, *PNEIGHBOR_OFFLOAD_STATE_DELEGATED, PNEIGHBOR_OFFLOAD_STATE_DELEGATED
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
req.alt-api: NEIGHBOR_OFFLOAD_STATE_DELEGATED
req.alt-loc: ndischimney.h
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

# _NEIGHBOR_OFFLOAD_STATE_DELEGATED structure



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NEIGHBOR_OFFLOAD_STATE_DELGATED structure contains the delegated variable of a neighbor state
  object.



## -syntax

````
typedef struct _NEIGHBOR_OFFLOAD_STATE_DELEGATED {
  OFFLOAD_STATE_HEADER Header;
  ULONG                NicReachabilityDelta;
} NEIGHBOR_OFFLOAD_STATE_DELEGATED, *PNEIGHBOR_OFFLOAD_STATE_DELEGATED;
````


## -struct-fields

### -field Header

An 
     <a href="netvista.offload_state_header">OFFLOAD_STATE_HEADER</a> structure. NDIS
     sets the 
     <b>Length</b> member of 
     <b>Header</b> to the size, in bytes, of the NEIGHBOR_OFFLOAD_STATE_DELEGATED structure. The 
     <b>RecognizedOptions</b> member of 
     <b>Header</b> is reserved.


### -field NicReachabilityDelta

The NIC's current time minus the 
     <b>NicReachabilityDelta</b> is the last time that the offload target confirmed neighbor reachability (see
     forward reachability in RFC 2461). For information about how the offload target uses this variable, see 
     <a href="netvista.ndismoffloadeventindicate">NdisMOffloadEventIndicate</a>. 
     <b>NicReachabilityDelta</b> is measured in units of clock ticks.


## -remarks
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
    <a href="netvista.ndis_miniport_offload_block_list">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure, which contains a header that is formatted as an 
    <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure. The 
    <b>Revision</b> member of the NDIS_OBJECT_HEADER structure, in this case, specifies the revision number of
    the NEIGHBOR_OFFLOAD_STATE_DELEGATED structure.


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
<a href="..\ndischimney\nc-ndischimney-w_query_offload_handler.md">MiniportQueryOffload</a>
</dt>
<dt>
<a href="..\ndischimney\nc-ndischimney-w_terminate_offload_handler.md">MiniportTerminateOffload</a>
</dt>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.neighbor_offload_state_cached">NEIGHBOR_OFFLOAD_STATE_CACHED</a>
</dt>
<dt>
<a href="netvista.neighbor_offload_state_const">NEIGHBOR_OFFLOAD_STATE_CONST</a>
</dt>
<dt>
<a href="netvista.offload_state_header">OFFLOAD_STATE_HEADER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NEIGHBOR_OFFLOAD_STATE_DELEGATED structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

