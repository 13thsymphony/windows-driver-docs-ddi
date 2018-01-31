---
UID : NF:ndis.NdisFreeReassembledNetBufferList
title : NdisFreeReassembledNetBufferList function
author : windows-driver-content
description : Call the NdisFreeReassembledNetBufferList function to free a reassembled NET_BUFFER_LIST structure and the associated NET_BUFFER structure and MDL chain.
old-location : netvista\ndisfreereassemblednetbufferlist.htm
old-project : netvista
ms.assetid : bcbb0c56-1500-45b2-bd20-03726ef7da77
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ndis/NdisFreeReassembledNetBufferList, netvista.ndisfreereassemblednetbufferlist, ndis_netbuf_functions_ref_604900da-90fb-4986-880e-8fea63c240a0.xml, NdisFreeReassembledNetBufferList, NdisFreeReassembledNetBufferList function [Network Drivers Starting with Windows Vista]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported in NDIS 6.0 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : Irql_NetBuffer_Function
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisFreeReassembledNetBufferList function
Call the 
  <b>NdisFreeReassembledNetBufferList</b> function to free a reassembled 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure and the associated 
  <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure and MDL chain.

## Syntax

````
VOID NdisFreeReassembledNetBufferList(
  _In_ PNET_BUFFER_LIST ReassembledNetBufferList,
  _In_ ULONG            DataOffsetDelta,
  _In_ ULONG            FreeReassembleFlags
);
````

## Parameters

`ReassembledNetBufferList`

A pointer to a NET_BUFFER_LIST structure that the driver allocated by calling the 
     <mshelp:link keywords="netvista.ndisallocatereassemblednetbufferlist" tabindex="0"><b>
     NdisAllocateReassembledNetBufferList</b></mshelp:link> function.

`DataOffsetDelta`

The number of bytes to advance (add to) the 
     <b>DataOffset</b> member of the reassembled NET_BUFFER structure before freeing the structure. This value
     should match 
     <i>DataOffsetDelta</i> that the driver passed to 
     <b>NdisAllocateReassembledNetBufferList</b>.

`FreeReassembleFlags`

NDIS flags that can be combined with an OR operation. Set this parameter to zero. There are
     currently no flags defined for this function.


## Return Value

None

## Remarks

<b>NdisFreeReassembledNetBufferList</b> frees a reassembled 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure that the caller
    allocated by calling 
    <mshelp:link keywords="netvista.ndisallocatereassemblednetbufferlist" tabindex="0"><b>
    NdisAllocateReassembledNetBufferList</b></mshelp:link>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_NetBuffer_Function |

## See Also

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>

<mshelp:link keywords="netvista.ndisallocatereassemblednetbufferlist" tabindex="0"><b>
   NdisAllocateReassembledNetBufferList</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFreeReassembledNetBufferList function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>