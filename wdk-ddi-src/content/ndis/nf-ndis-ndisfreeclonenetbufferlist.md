---
UID: NF.ndis.NdisFreeCloneNetBufferList
title: NdisFreeCloneNetBufferList function
author: windows-driver-content
description: Call the NdisFreeCloneNetBufferList function to free a NET_BUFFER_LIST structure and all associated NET_BUFFER structures and MDL chains that were previously allocated by calling the NdisAllocateCloneNetBufferList function.
old-location: netvista\ndisfreeclonenetbufferlist.htm
old-project: netvista
ms.assetid: 3c632d54-8eb2-475b-8cdf-363028f67437
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: NdisFreeCloneNetBufferList
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
req.alt-api: NdisFreeCloneNetBufferList
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_NetBuffer_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# NdisFreeCloneNetBufferList function



## -description
Call the 
  <b>NdisFreeCloneNetBufferList</b> function to free a 
  <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure and all associated 
  <a href="netvista.net_buffer">NET_BUFFER</a> structures and MDL chains that were
  previously allocated by calling the 
  <a href="netvista.ndisallocateclonenetbufferlist">
  NdisAllocateCloneNetBufferList</a> function.


## -syntax

````
VOID NdisFreeCloneNetBufferList(
  _In_ PNET_BUFFER_LIST CloneNetBufferList,
  _In_ ULONG            FreeCloneFlags
);
````


## -parameters

### -param CloneNetBufferList [in]

A pointer to a NET_BUFFER_LIST structure that was allocated by calling 
     <b>NdisAllocateCloneNetBufferList</b>.

### -param FreeCloneFlags [in]

NDIS flags that can be combined with an OR operation. The following flags are defined:
     


### -param NDIS_CLONE_FLAGS_RESERVED

Reserved for NDIS.

### -param NDIS_CLONE_FLAGS_USE_ORIGINAL_MDLS

If this flag is set, NDIS did not allocate new MDLs for the cloned NET_BUFFER_LIST in the 
       <a href="netvista.ndisallocateclonenetbufferlist">
       NdisAllocateCloneNetBufferList</a> function. Instead, the cloned NET_BUFFER_LIST used the same MDL
       chain as in the original NET_BUFFER_LIST. If NDIS_CLONE_FLAGS_USE_ORIGINAL_MDLS is cleared, NDIS
       allocated new MDLs to reference the original data buffers.
</dd>
</dl>

## -returns
None

## -remarks
The caller must specifiy the same flags that it specified in the 
    <i>AllocateCloneFlags</i> parameter when it called the 
    <a href="netvista.ndisallocateclonenetbufferlist">
    NdisAllocateCloneNetBufferList</a> function.

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
Version
</th>
<td width="70%">
Supported in NDIS 6.0 and later.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
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
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= DISPATCH_LEVEL
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.ndis_irql_netbuffer_function">Irql_NetBuffer_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.net_buffer">NET_BUFFER</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="netvista.ndisallocateclonenetbufferlist">
   NdisAllocateCloneNetBufferList</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFreeCloneNetBufferList function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
