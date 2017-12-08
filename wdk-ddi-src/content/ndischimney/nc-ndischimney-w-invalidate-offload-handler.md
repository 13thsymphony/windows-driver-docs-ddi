---
UID: NC.ndischimney.W_INVALIDATE_OFFLOAD_HANDLER
title: W_INVALIDATE_OFFLOAD_HANDLER
author: windows-driver-content
description: The MiniportInvalidateOffload function invalidates previously offloaded TCP chimney state objects.
old-location: netvista\miniportinvalidateoffload.htm
old-project: netvista
ms.assetid: 58226149-daea-40aa-afb6-13ce615434b3
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: BINARY_DATA, BINARY_DATA
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
req.alt-api: MiniportInvalidateOffload
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
req.irql: Any level
req.iface: 
---

# W_INVALIDATE_OFFLOAD_HANDLER callback



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]</p>
<p>The 
  <i>MiniportInvalidateOffload</i> function invalidates previously offloaded TCP chimney state objects.</p>


## -prototype

````
W_INVALIDATE_OFFLOAD_HANDLER MiniportInvalidateOffload;

VOID MiniportInvalidateOffload(
  _In_ NDIS_HANDLE                       MiniportAdapterContext,
  _In_ PNDIS_MINIPORT_OFFLOAD_BLOCK_LIST OffloadBlockList
)
{ ... }
````


## -parameters
<dl>

### -param MiniportAdapterContext [in]

<dd>
<p>The handle to an offload-target allocated context area in which the offload target maintains state
     information about this instance of the adapter. The offload target provided this handle to NDIS when it
     called 
     <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">
     NdisMSetMiniportAttributes</a> from its 
     <a href="..\ndis\nc-ndis-miniport-initialize.md">
     MiniportInitializeEx</a> function.</p>
</dd>

### -param OffloadBlockList [in]

<dd>
<p>A pointer to an 
     <a href="..\ndischimney\ns-ndischimney--ndis-miniport-offload-block-list.md">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure, which can be the root of a linked list of such
     structures. These structures identify the offloaded state object that is being invalidated.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The 
    <i>MiniportInvalidateOffload</i> function stores the 
    <i>OffloadBlockList</i> pointer and then returns. The offload target always completes the invalidate
    operation asynchronously by calling 
    <a href="..\ndischimney\nf-ndischimney-ndisminvalidateoffloadcomplete.md">
    NdisMInvalidateOffloadComplete</a>.</p>

<p>The tree passed to the 
    <i>MiniportInvalidateOffload</i> function contains only NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures. The
    tree does not contain any 
    <a href="netvista.offload_state_structures">offload state structures</a>. That is,
    there are no such structures following the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures in memory.</p>

<p>The NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structures in the tree indicate the state object to be
    invalidated. A non-NULL 
    <b>*MiniportOffloadContext</b> member points to a memory location containing a PVOID value that was
    supplied by the offload target when the state object was offloaded. For more information, see 
    <a href="netvista.storing_and_referencing_offloaded_state">Storing and Referencing
    Offloaded State</a>. This PVOID value references the miniport offload context in which the offload
    target stores the state object to be invalidated.</p>

<p>For information about an offload target's treatment of invalidated state objects, see 
    <a href="netvista.handling_invalidated_state_objects">Treatment of Invalidated State
    Objects</a>.</p>

<p>Eventually, the host stack will 
    <a href="netvista.terminating_offload_state">terminate the offload of the invalidated
    state object</a>. However, until that time, the offload target owns the invalidated state object. The
    offload target must not free the resources for the invalidated state object until the host stack has
    terminated the offload of that state object. The offload target must not use the invalidated state object
    or any TCP connections that depend on that state object for sending data.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndischimney.h (include Ndischimney.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndischimney\ns-ndischimney--ndis-miniport-offload-block-list.md">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>
</dt>
<dt>
<a href="..\ndischimney\nf-ndischimney-ndisminvalidateoffloadcomplete.md">
   NdisMInvalidateOffloadComplete</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20W_INVALIDATE_OFFLOAD_HANDLER callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
