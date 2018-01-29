---
UID : NF:ndischimney.NdisQueryOffloadState
title : NdisQueryOffloadState function
author : windows-driver-content
description : A protocol or intermediate driver calls the NdisQueryOffloadState function to query previously offloaded TCP chimney state objects.
old-location : netvista\ndisqueryoffload.htm
old-project : netvista
ms.assetid : 97d30ba7-b67c-460b-ba80-171687495e27
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : NdisQueryOffloadState function [Network Drivers Starting with Windows Vista], ndis/NdisQueryOffloadState, NdisQueryOffloadState, tcp_chim_ndis_func_9075e6da-2950-4643-b626-36b4a9ce5a33.xml, netvista.ndisqueryoffload
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
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PD_BUFFER_VIRTUAL_SUBNET_INFO
---


# NdisQueryOffloadState function
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

A protocol or intermediate driver calls the 
  <b>NdisQueryOffloadState</b> function to query previously offloaded TCP chimney state objects.

## Syntax

````
VOID NdisQueryOffloadState(
  _In_ NDIS_HANDLE                       NdisBindingHandle,
  _In_ PNDIS_PROTOCOL_OFFLOAD_BLOCK_LIST OffloadBlockList
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
     <mshelp:link keywords="netvista.ndis_protocol_offload_block_list" tabindex="0"><b>
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</b></mshelp:link> structure that can be a stand-alone structure or the root of a
     linked list of such structures. These structures identify the offloaded state objects that are being
     queried.


## Return Value

None

## Remarks

An intermediate driver calls the 
    <b>NdisQueryOffloadState</b> function to propagate a query offload operation that was initiated by the host
    stack. For more information, see 
    <mshelp:link keywords="netvista.propagating_state_manipulation_operations" tabindex="0">Propagating
    State-Manipulation Operations</mshelp:link>.

From the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure that was passed to its 
    <a href="..\ndischimney\nc-ndischimney-w_query_offload_handler.md">MiniportQueryOffload</a> function, the
    intermediate driver constructs an NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure. For more information, see
    Reusing an 
    <mshelp:link keywords="netvista.ndis_miniport_offload_block_list" tabindex="0"><b>
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</b></mshelp:link> Structure. The intermediate driver passes a pointer (the 
    <i>OffloadBlockList</i> parameter) to this NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure when calling the 
    <b>NdisQueryOffloadState</b> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndischimney.h (include Ndischimney.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<mshelp:link keywords="netvista.ndismqueryoffloadstatecomplete" tabindex="0"><b>
   NdisMQueryOffloadStateComplete</b></mshelp:link>

<a href="..\ndischimney\nc-ndischimney-w_query_offload_handler.md">MiniportQueryOffload</a>

<mshelp:link keywords="netvista.ndis_miniport_offload_block_list" tabindex="0"><b>
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</b></mshelp:link>

<mshelp:link keywords="netvista.protocolqueryoffloadcomplete" tabindex="0"><i>
   ProtocolQueryOffloadComplete</i></mshelp:link>

<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>

<mshelp:link keywords="netvista.ndis_protocol_offload_block_list" tabindex="0"><b>
   NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisQueryOffloadState function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>