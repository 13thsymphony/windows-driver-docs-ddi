---
UID: NF:ndischimney.NdisMUpdateOffloadComplete
title: NdisMUpdateOffloadComplete function
author: windows-driver-content
description: An offload target calls the NdisMUpdateOffloadComplete function to complete an update offload operation that was initiated by a previous call to the MiniportUpdateOffload function of the offload target.
old-location: netvista\ndismupdateoffloadcomplete.htm
old-project: netvista
ms.assetid: aa2c549c-eb16-4d59-9280-1913c8c0266a
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisMUpdateOffloadComplete, NdisMUpdateOffloadComplete function [Network Drivers Starting with Windows Vista], ndischimney/NdisMUpdateOffloadComplete, netvista.ndismupdateoffloadcomplete, tcp_chim_ndis_func_c525f7d7-2a4d-47ef-8337-85551fb1f7ab.xml
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
-	HeaderDef
api_location:
-	ndischimney.h
api_name:
-	NdisMUpdateOffloadComplete
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---


# NdisMUpdateOffloadComplete function
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

An offload target calls the 
  <b>NdisMUpdateOffloadComplete</b> function to complete an update offload operation that was initiated by a
  previous call to the 
  <a href="..\ndischimney\nc-ndischimney-w_update_offload_handler.md">MiniportUpdateOffload</a> function of
  the offload target.

## Syntax

````
VOID NdisMUpdateOffloadComplete(
  _In_ NDIS_HANDLE                       NdisMiniportHandle,
  _In_ PNDIS_MINIPORT_OFFLOAD_BLOCK_LIST OffloadBlockList
);
````

## Parameters

`NdisMiniportHandle`

The handle that the offload target obtained in a previous call to 
     <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
     NdisMRegisterMiniportDriver</a>.

`OffloadBlockList`

A pointer to an 
     <a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure. The offload target obtained this pointer as an input
     parameter to its 
     <a href="..\ndischimney\nc-ndischimney-w_update_offload_handler.md">
     MiniportUpdateOffload</a> function.


## Return Value

None

## Remarks

Before calling the 
    <b>NdisMUpdateOffloadComplete</b> function, the offload target must write either of the following
    NDIS_STATUS values to the 
    <b>Status</b> member of each NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure in the state tree:

<ul>
<li>
NDIS_STATUS_SUCCESS

The offload target successfully updated the state object variables and/or successfully updated
      path-to-neighbor links.

</li>
<li>
NDIS_STATUS_FAILURE

The update operation did not succeed. The offload target should continue normal processing on the
      connection. The host stack will terminate the offload of state objects that could not be updated.

</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ndischimney.h (include Ndischimney.h) |
| **IRQL** | Any level |

## See Also

<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>



<a href="..\ndischimney\nc-ndischimney-w_update_offload_handler.md">MiniportUpdateOffload</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>