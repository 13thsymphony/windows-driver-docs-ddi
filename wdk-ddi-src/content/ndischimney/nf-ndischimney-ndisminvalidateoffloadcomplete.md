---
UID: NF.ndischimney.NdisMInvalidateOffloadComplete
title: NdisMInvalidateOffloadComplete function
author: windows-driver-content
description: An offload target calls the NdisMInvalidateOffloadComplete function to complete an invalidate offload operation that was initiated by a previous call to the MiniportInvalidateOffload function of the offload target.
old-location: netvista\ndisminvalidateoffloadcomplete.htm
old-project: NetVista
ms.assetid: fd14e983-ea4b-41f2-973d-88b114306e75
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisMInvalidateOffloadComplete
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
req.alt-api: NdisMInvalidateOffloadComplete
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
req.irql: Any level
---

# NdisMInvalidateOffloadComplete function



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

An offload target calls the 
  <b>NdisMInvalidateOffloadComplete</b> function to complete an invalidate offload operation that was
  initiated by a previous call to the 
  <a href="..\ndischimney\nc-ndischimney-w_invalidate_offload_handler.md">
  MiniportInvalidateOffload</a> function of the offload target.



## -syntax

````
VOID NdisMInvalidateOffloadComplete(
  _In_ NDIS_HANDLE                       NdisMiniportHandle,
  _In_ PNDIS_MINIPORT_OFFLOAD_BLOCK_LIST OffloadBlockList
);
````


## -parameters

### -param NdisMiniportHandle [in]

The handle that the offload target obtained in a previous call to the 
     <a href="netvista.ndismregisterminiportdriver">
     NdisMRegisterMiniportDriver</a> function.


### -param OffloadBlockList [in]

A pointer to an 
     <a href="netvista.ndis_miniport_offload_block_list">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure. The ofload target obtained this pointer as an input
     parameter to its 
     <a href="..\ndischimney\nc-ndischimney-w_invalidate_offload_handler.md">
     MiniportInvalidateOffload</a> function.


## -returns
None


## -remarks
Before calling the 
    <b>NdisMInvalidateOffloadComplete</b> function, the offload target must write either of the following
    NDIS_STATUS values to the 
    <b>Status</b> member of each NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure in the state tree:

NDIS_STATUS_SUCCESS
     

The offload target successfully invalidated the state objects.

NDIS_STATUS_FAILURE
     

The invalidate operation did not succeed. In this case, the offload target has stopped responding (is
     hung).


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
IRQL

</th>
<td width="70%">
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndischimney\nc-ndischimney-w_invalidate_offload_handler.md">MiniportInvalidateOffload</a>
</dt>
<dt>
<a href="netvista.ndis_miniport_offload_block_list">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>
</dt>
<dt>
<a href="netvista.ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisMInvalidateOffloadComplete function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

