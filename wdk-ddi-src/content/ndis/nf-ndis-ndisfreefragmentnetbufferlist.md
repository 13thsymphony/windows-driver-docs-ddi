---
UID: NF:ndis.NdisFreeFragmentNetBufferList
title: NdisFreeFragmentNetBufferList function
author: windows-driver-content
description: Call the NdisFreeFragmentNetBufferList function to free a NET_BUFFER_LIST structure and all associated NET_BUFFER structures and MDL chains that were previously allocated by the calling NdisAllocateFragmentNetBufferList function.
old-location: netvista\ndisfreefragmentnetbufferlist.htm
old-project: netvista
ms.assetid: 2bbf85ee-8541-4d3d-87e5-0633bc35670b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndisfreefragmentnetbufferlist, ndis_netbuf_functions_ref_e88011a7-4c83-4736-8a3f-3a2d1c3b2e6f.xml, NdisFreeFragmentNetBufferList function [Network Drivers Starting with Windows Vista], ndis/NdisFreeFragmentNetBufferList, NdisFreeFragmentNetBufferList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_NetBuffer_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisFreeFragmentNetBufferList
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisFreeFragmentNetBufferList function
Call the 
  <b>NdisFreeFragmentNetBufferList</b> function to free a 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure and all associated 
  <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures and MDL chains that were
  previously allocated by the calling 
  <a href="..\ndis\nf-ndis-ndisallocatefragmentnetbufferlist.md">
  NdisAllocateFragmentNetBufferList</a> function.

## Syntax

````
VOID NdisFreeFragmentNetBufferList(
  _In_ PNET_BUFFER_LIST FragmentNetBufferList,
  _In_ ULONG            DataOffsetDelta,
  _In_ ULONG            FreeFragmentFlags
);
````

## Parameters

`FragmentNetBufferList`

A pointer to a NET_BUFFER_LIST structure that was allocated by calling 
     <b>NdisAllocateFragmentNetBufferList</b>.

`DataOffsetDelta`

The amount, in bytes, to advance (add to the data offset) the fragment NET_BUFFER structures
     before freeing them. This value should match the value of the 
     <i>DataOffsetDelta</i> parameter that was passed to 
     <b>NdisAllocateFragmentNetBufferList</b> when the NET_BUFFER_LIST structure was created.

`FreeFragmentFlags`

NDIS flags that can be combined with an OR operation. Set this parameter to zero. There are
     currently no flags defined for this function.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later. Supported in NDIS 6.0 and later. |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_NetBuffer_Function |

## See Also

<a href="..\ndis\nf-ndis-ndisallocatefragmentnetbufferlist.md">
   NdisAllocateFragmentNetBufferList</a>

<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFreeFragmentNetBufferList function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>