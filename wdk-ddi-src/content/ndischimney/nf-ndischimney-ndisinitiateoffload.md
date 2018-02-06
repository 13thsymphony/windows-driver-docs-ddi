---
UID: NF:ndischimney.NdisInitiateOffload
title: NdisInitiateOffload function
author: windows-driver-content
description: A protocol or intermediate driver calls the NdisInitiateOffload function to offload TCP chimney state objects.
old-location: netvista\ndisinitiateoffload.htm
old-project: netvista
ms.assetid: a1979227-a447-4dd3-8a5d-7986362020cd
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: tcp_chim_ndis_func_c93e8055-91b1-42d4-a227-6b21086c6e7b.xml, NdisInitiateOffload function [Network Drivers Starting with Windows Vista], netvista.ndisinitiateoffload, NdisInitiateOffload, ndischimney/NdisInitiateOffload
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
req.lib: Ndis.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisInitiateOffload
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---


# NdisInitiateOffload function
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

A protocol or intermediate driver calls the 
  <b>NdisInitiateOffload</b> function to offload TCP chimney state objects.

## Syntax

````
VOID NdisInitiateOffload(
  _In_    NDIS_HANDLE                       NdisBindingHandle,
  _Inout_ PNDIS_PROTOCOL_OFFLOAD_BLOCK_LIST OffloadBlockList
);
````

## Parameters

`NdisBindingHandle`

The handle that NDIS provided at the 
     <i>NdisBindingHandle</i> parameter of 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>. This handle
     identifies the binding between the caller and the underlying intermediate driver or offload
     target.

`OffloadBlockList`

A pointer to an 
     <a href="..\ndischimney\ns-ndischimney-_ndis_protocol_offload_block_list.md">
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a> structure that can be a stand-alone structure or the root of a
     linked list of such structures. These structures identify the state that is being offloaded.


## Return Value

None

## Remarks

An intermediate driver calls the 
    <b>NdisInitiateOffload</b> function to propagate an initiate offload operation that was initiated by the
    host stack. For more information, see 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff563771">Propagating
    State-Manipulation Operations</a>.

From the 
    <a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure that was passed to its 
    <i>MiniportInitiateOffload</i> function, the intermediate driver constructs an
    NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure. For more information, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/reusing-an-ndis-miniport-offload-block-list-structure">Reusing an
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST Structure</a>. The intermediate driver passes a pointer (the 
    <i>OffloadBlockList</i> parameter) to this NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure when calling the 
    <b>NdisInitiateOffload</b> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ndischimney.h (include Ndischimney.h) |
| **Library** | Ndis.lib |

## See Also

<a href="..\ndischimney\nc-ndischimney-w_initiate_offload_handler.md">MiniportInitiateOffload</a>

<a href="..\ndischimney\ns-ndischimney-_ndis_protocol_offload_block_list.md">
   NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a>

<a href="..\ndischimney\nf-ndischimney-ndisminitiateoffloadcomplete.md">NdisMInitiateOffloadComplete</a>

<a href="..\ndischimney\nc-ndischimney-initiate_offload_complete_handler.md">
   ProtocolInitiateOffloadComplete</a>

<a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>

<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisInitiateOffload function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>