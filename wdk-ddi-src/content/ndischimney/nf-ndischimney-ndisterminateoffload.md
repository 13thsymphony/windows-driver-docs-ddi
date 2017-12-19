---
UID: NF.ndischimney.NdisTerminateOffload
title: NdisTerminateOffload function
author: windows-driver-content
description: A protocol driver or intermediate driver calls the NdisTerminateOffload function to terminate the offload of one or more state objects
old-location: netvista\ndisterminateoffload.htm
old-project: NetVista
ms.assetid: 13eb4c17-2cb5-4773-b2e3-e8e624473c97
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisTerminateOffload
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisTerminateOffload
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: 
---

# NdisTerminateOffload function



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

A protocol driver or intermediate driver calls the 
  <b>NdisTerminateOffload</b> function to terminate the offload of one or more state objects



## -syntax

````
VOID NdisTerminateOffload(
  _In_    NDIS_HANDLE                       NdisBindingHandle,
  _Inout_ PNDIS_PROTOCOL_OFFLOAD_BLOCK_LIST OffloadBlockList
);
````


## -parameters

### -param NdisBindingHandle [in]

The handle that NDIS provided at the 
     <i>NdisBindingHandle</i> parameter of 
     <a href="netvista.ndisopenadapterex">NdisOpenAdapterEx</a>. This handle
     identifies the binding between the caller and the underlying intermediate driver or offload
     target.


### -param OffloadBlockList [in, out]

A pointer to an 
     <a href="netvista.ndis_protocol_offload_block_list">
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a> structure that can be a stand-alone structure or the root of a
     linked list of such structures. These structures identify the offloaded state objects that are being
     terminated.


## -returns
None


## -remarks
An intermediate driver calls the 
    <b>NdisTerminateOffload</b> function to propagate a terminate offload operation that was initiated by the
    host stack. For more information, see 
    <a href="netvista.propagating_state_manipulation_operations">Propagating
    State-Manipulation Operations</a>.

From the 
    <a href="netvista.ndis_miniport_offload_block_list">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure that was passed to its 
    <i>MiniportTerminateOffload</i> function, the intermediate driver constructs an
    NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure. For more information, see 
    <a href="netvista.reusing_an_ndis_miniport_offload_block_list_structure">Reusing an
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST Structure</a>. The intermediate driver passes a pointer (the 
    <i>OffloadBlockList</i> parameter) to this NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure when calling the 
    <b>NdisTerminateOffload</b> function.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
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
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndischimney\nc-ndischimney-w_terminate_offload_handler.md">MiniportTerminateOffload</a>
</dt>
<dt>
<a href="netvista.ndis_miniport_offload_block_list">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>
</dt>
<dt>
<a href="netvista.ndismterminateoffloadcomplete">
   NdisMTerminateOffloadComplete</a>
</dt>
<dt>
<a href="netvista.ndisopenadapterex">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="netvista.ndis_protocol_offload_block_list">
   NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a>
</dt>
<dt>
<a href="..\ndischimney\nc-ndischimney-terminate_offload_complete_handler.md">
   ProtocolTerminateOffloadComplete</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisTerminateOffload function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

