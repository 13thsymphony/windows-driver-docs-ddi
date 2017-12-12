---
UID: NF.ndis.NdisFreeNetBufferList
title: NdisFreeNetBufferList function
author: windows-driver-content
description: Call the NdisFreeNetBufferList function to free a NET_BUFFER_LIST structure that was previously allocated from a NET_BUFFER_LIST structure pool.
old-location: netvista\ndisfreenetbufferlist.htm
old-project: netvista
ms.assetid: fddfe5f8-900a-4f4c-8c78-a106a4a54d88
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisFreeNetBufferList
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
req.alt-api: NdisFreeNetBufferList
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

# NdisFreeNetBufferList function



## -description
Call the 
  <b>NdisFreeNetBufferList</b> function to free a 
  <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure that was previously
  allocated from a NET_BUFFER_LIST structure pool.



## -syntax

````
VOID NdisFreeNetBufferList(
  _In_ PNET_BUFFER_LIST NetBufferList
);
````


## -parameters

### -param NetBufferList [in]

A pointer to a NET_BUFFER_LIST structure that was allocated by calling the 
     <a href="netvista.ndisallocatenetbufferlist">NdisAllocateNetBufferList</a> or 
     <a href="netvista.ndisallocatenetbufferandnetbufferlist">
     NdisAllocateNetBufferAndNetBufferList</a> function.


## -returns
None


## -remarks
To allocate a 
    <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure from a pool, call
    the 
    <a href="netvista.ndisallocatenetbufferlist">NdisAllocateNetBufferList</a> or 
    <a href="netvista.ndisallocatenetbufferandnetbufferlist">
    NdisAllocateNetBufferAndNetBufferList</a> function.

The 
    <a href="netvista.net_buffer">NET_BUFFER</a> structures that are associated with
    the NET_BUFFER_LIST structure are not freed unless they were preallocated with the NET_BUFFER_LIST
    structure. You can reuse any NET_BUFFER structures that were not preallocated or you should free such
    structures separately.

If you allocated context space for a NET_BUFFER_LIST structure with the 
    <a href="netvista.ndisallocatenetbufferlistcontext">
    NdisAllocateNetBufferListContext</a> function, you must free such context space before you free the
    NET_BUFFER_LIST structure. You must not attempt to free the context space that you allocated with 
    <b>NdisAllocateNetBufferList</b> or 
    <b>NdisAllocateNetBufferAndNetBufferList</b> by specifying the 
    <i>ContextSize</i> and 
    <i>ContextBackFill</i> parameters.


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
<a href="netvista.ndisallocatenetbufferandnetbufferlist">
   NdisAllocateNetBufferAndNetBufferList</a>
</dt>
<dt>
<a href="netvista.ndisallocatenetbufferlist">NdisAllocateNetBufferList</a>
</dt>
<dt>
<a href="netvista.ndisallocatenetbufferlistcontext">
   NdisAllocateNetBufferListContext</a>
</dt>
<dt>
<a href="netvista.net_buffer">NET_BUFFER</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFreeNetBufferList function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

