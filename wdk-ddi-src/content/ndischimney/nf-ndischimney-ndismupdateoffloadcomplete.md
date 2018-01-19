---
UID : NF:ndischimney.NdisMUpdateOffloadComplete
title : NdisMUpdateOffloadComplete function
author : windows-driver-content
description : An offload target calls the NdisMUpdateOffloadComplete function to complete an update offload operation that was initiated by a previous call to the MiniportUpdateOffload function of the offload target.
old-location : netvista\ndismupdateoffloadcomplete.htm
old-project : netvista
ms.assetid : aa2c549c-eb16-4d59-9280-1913c8c0266a
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : NdisMUpdateOffloadComplete
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndischimney.h
req.include-header : Ndischimney.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NdisMUpdateOffloadComplete
req.alt-loc : ndischimney.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : Any level
req.typenames : PD_BUFFER_VIRTUAL_SUBNET_INFO
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

NDIS_STATUS_SUCCESS

The offload target successfully updated the state object variables and/or successfully updated
      path-to-neighbor links.

NDIS_STATUS_FAILURE

The update operation did not succeed. The offload target should continue normal processing on the
      connection. The host stack will terminate the offload of state objects that could not be updated.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndischimney.h (include Ndischimney.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ndischimney\nc-ndischimney-w_update_offload_handler.md">MiniportUpdateOffload</a>
</dt>
<dt>
<a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMUpdateOffloadComplete function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>