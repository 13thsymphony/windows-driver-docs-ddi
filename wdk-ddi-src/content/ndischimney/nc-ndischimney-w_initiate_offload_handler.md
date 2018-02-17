---
UID: NC:ndischimney.W_INITIATE_OFFLOAD_HANDLER
title: W_INITIATE_OFFLOAD_HANDLER
author: windows-driver-content
description: MiniportInitiateOffload offloads TCP chimney state from the host stack.
old-location: netvista\miniportinitiateoffload.htm
old-project: netvista
ms.assetid: f430642b-01bf-4ed7-bfea-e8dd8d5a8208
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportinitiateoffload, MiniportInitiateOffload callback function [Network Drivers Starting with Windows Vista], MiniportInitiateOffload, W_INITIATE_OFFLOAD_HANDLER, W_INITIATE_OFFLOAD_HANDLER, ndischimney/MiniportInitiateOffload, tcp_chim_miniport_func_58c338e0-ea8e-41c2-a781-a32f4be7758c.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ndischimney.h
apiname:
-	MiniportInitiateOffload
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---


# W_INITIATE_OFFLOAD_HANDLER callback function
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

<i>MiniportInitiateOffload</i> offloads TCP chimney state from the host stack.

## Syntax

```
W_INITIATE_OFFLOAD_HANDLER WInitiateOffloadHandler;

void WInitiateOffloadHandler(
  IN NDIS_HANDLE MiniportAdapterContext,
  IN OUT PNDIS_MINIPORT_OFFLOAD_BLOCK_LIST OffloadBlockList
)
{...}
```

## Parameters

`MiniportAdapterContext`

The handle to an offload-target allocated context area in which the offload target maintains state
     information about this instance of the adapter. The miniport driver provided this handle to NDIS when it
     called 
     <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">
     NdisMSetMiniportAttributes</a> from its 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">
     MiniportInitializeEx</a> function.

`OffloadBlockList`

A pointer to an 
     <a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure that can be a stand-alone structure or the root of a
     linked list of such structures.


## Return Value

None

## Remarks

The 
    <i>MiniportInitiateOffload</i> function stores the 
    <i>OffloadBlockList</i> pointer and then returns. The offload target always completes the offload
    operation asynchronously by calling 
    <a href="..\ndischimney\nf-ndischimney-ndisminitiateoffloadcomplete.md">
    NdisMInitiateOffloadComplete</a>. The state tree pointed to by the 
    <i>OffloadBlockList</i> pointer is valid until the miniport driver calls 
    <b>NdisMInitiateOffloadComplete</b>.

After returning from its 
    <i>MiniportInitiateOffload</i> function, the offload target offloads state from the state tree. An
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure whose 
    <b>MiniportOffloadContext</b> member points to a memory location that contains a <b>NULL</b> value is followed by
    state to be offloaded. For more information, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/storing-and-referencing-offloaded-state">Storing and Referencing
    Offloaded State</a>. The 
    <b>Header</b> member of an NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure contains a 
    <b>Type</b> member that specifies the type of offload state, and by implication, the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570939">offload state structure</a> or structures,
    that immediately follow the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure in memory.

The offload target offloads the offload state associated with an NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
    structure into an offload context area. For more information, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/storing-and-referencing-offloaded-state">Storing and Referencing
    Offloaded State</a>.

When offloading state, the offload target must traverse the state tree in 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/traversing-a-state-tree">depth-first/breadth-next fashion</a>. It
    is critical that an offload target offloads state in this way.

Some of the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures in the state tree that are passed to the 
    <i>MiniportInitiateOffload</i> function can be placeholders or linking nodes that do not have accompanying
    state to be offloaded. For more information, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/placeholders--linkers--and-new-offloads">Placeholders, Linkers, and
    New Offloads</a>.

The offload target can receive buffered data from the host stack for a connection that is being
    offloaded. The offload target must copy this data into its own buffer before completing the offload
    operation. For more information about processing buffered receive data, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/handling-buffered-receive-data-during-and-after-an-offload-operation">
    Handling Buffered Receive Data During and After an Offload Operation</a>.

For each state object that it offloads, the offload target must also supply a PVOID value that
    references the offload context area in which the offload target stores the state object. The offload
    target writes this PVOID value to the memory location pointed to by the 
    <b>*MiniportOffloadContext</b> member of the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure associated with
    the state. If the offload target did not successfully offload the state associated with the
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure, it should not write a value to the memory location pointed to
    by the 
    <b>*MiniportOffloadContext</b> member. For more information, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/storing-and-referencing-offloaded-state">Storing and Referencing
    Offloaded State</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ndischimney.h (include Ndischimney.h) |
| **IRQL** | Any level |

## See Also

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>



<a href="..\ndischimney\nf-ndischimney-ndisminitiateoffloadcomplete.md">NdisMInitiateOffloadComplete</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20W_INITIATE_OFFLOAD_HANDLER callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>