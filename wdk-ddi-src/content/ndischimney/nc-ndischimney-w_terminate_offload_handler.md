---
UID: NC:ndischimney.W_TERMINATE_OFFLOAD_HANDLER
title: W_TERMINATE_OFFLOAD_HANDLER
author: windows-driver-content
description: The MiniportTerminateOffload function terminates the offload of one or more state objects.
old-location: netvista\miniportterminateoffload.htm
old-project: netvista
ms.assetid: 1b808e3c-2d64-44c9-88d3-0a0311e1dc99
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: MiniportTerminateOffload, MiniportTerminateOffload callback function [Network Drivers Starting with Windows Vista], W_TERMINATE_OFFLOAD_HANDLER, ndischimney/MiniportTerminateOffload, netvista.miniportterminateoffload, tcp_chim_miniport_func_73171220-b803-4d9e-bf13-fe4daebbe5dc.xml
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndischimney.h
api_name:
-	MiniportTerminateOffload
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---


# W_TERMINATE_OFFLOAD_HANDLER callback function
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The 
  <i>MiniportTerminateOffload</i> function terminates the offload of one or more state objects.

## Syntax

```
W_TERMINATE_OFFLOAD_HANDLER WTerminateOffloadHandler;

void WTerminateOffloadHandler(
  IN NDIS_HANDLE MiniportAdapterContext,
  IN OUT PNDIS_MINIPORT_OFFLOAD_BLOCK_LIST OffloadBlockList
)
{...}
```

## Parameters

`MiniportAdapterContext`

The handle to an offload-target allocated context area in which the offload target maintains state
     information about this instance of the adapter. The offload target provided this handle to NDIS when it
     called 
     <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">
     NdisMSetMiniportAttributes</a> from its 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">
     MiniportInitializeEx</a> function.

`OffloadBlockList`

A pointer to an 
     <a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure, which can be the root of a linked list of such
     structures. These structures identify the offloaded state objects that are being terminated.


## Return Value

None

## Remarks

The 
    <i>MiniportTerminateOffload</i> function stores the 
    <i>OffloadBlockList</i> pointer and then returns. The offload target always completes the terminate
    operation asynchronously by calling the 
    <a href="..\ndischimney\nf-ndischimney-ndismterminateoffloadcomplete.md">
    NdisMTerminateOffloadComplete</a> function.

The 
    <i>OffloadBlockList</i> pointer points to an NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure that can be either
    a stand-alone structure or the root block list in an 
    <a href="https://msdn.microsoft.com/c96608bd-5e8f-499b-872a-b6f7f33c9e0c">offload state tree</a> that contains multiple
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures. Such block lists, as well as any 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570939">offload state structures</a> that are
    associated with them, are valid until the miniport driver calls the 
    <b>NdisMTerminateOffloadComplete</b> function.

Each NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure can be immediately followed in memory by a delegated
    state structure (<i>XXX</i>_OFFLOAD_STATE_DELEGATED). The offload target copies delegated variable values into the
    delegated state structures supplied by the host stack.

The host stack will not request the termination of the offload of a TCP connection until both of the
    following conditions are met:

<ul>
<li>
All the outstanding invalidate, query, and update requests pertaining to that connection have
      completed.

</li>
<li>
All outstanding receive and disconnect calls have returned.

</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ndischimney.h (include Ndischimney.h) |
| **IRQL** | Any level |

## See Also

<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="..\ndischimney\nf-ndischimney-ndismterminateoffloadcomplete.md">
   NdisMTerminateOffloadComplete</a>



<a href="..\ndischimney\ns-ndischimney-_tcp_offload_state_delegated.md">TCP_OFFLOAD_STATE_DELEGATED</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>