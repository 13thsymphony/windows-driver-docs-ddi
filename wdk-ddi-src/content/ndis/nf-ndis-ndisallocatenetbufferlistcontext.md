---
UID: NF.ndis.NdisAllocateNetBufferListContext
title: NdisAllocateNetBufferListContext function
author: windows-driver-content
description: Call the NdisAllocateNetBufferListContext function to allocate more context space in the NET_BUFFER_LIST_CONTEXT structure of a NET_BUFFER_LIST structure.
old-location: netvista\ndisallocatenetbufferlistcontext.htm
old-project: netvista
ms.assetid: 3bbad723-86bf-4206-9e51-52a66efaec20
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisAllocateNetBufferListContext
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
req.alt-api: NdisAllocateNetBufferListContext
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

# NdisAllocateNetBufferListContext function



## -description
Call the 
  <b>NdisAllocateNetBufferListContext</b> function to allocate more context space in the 
  <a href="netvista.net_buffer_list_context">NET_BUFFER_LIST_CONTEXT</a> structure of a
  
  <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure.



## -syntax

````
NDIS_STATUS NdisAllocateNetBufferListContext(
  _In_ PNET_BUFFER_LIST NetBufferList,
  _In_ USHORT           ContextSize,
  _In_ USHORT           ContextBackFill,
  _In_ ULONG            PoolTag
);
````


## -parameters

### -param NetBufferList [in]

A pointer to a previously allocated NET_BUFFER_LIST structure.


### -param ContextSize [in]

The amount of context space to allocate in the NET_BUFFER_LIST_CONTEXT structure. This amount must
     be a multiple of the value defined by MEMORY_ALLOCATION_ALIGNMENT.


### -param ContextBackFill [in]

The amount of memory, in addition to the value of 
     <i>ContextSize</i>, to allocate if NDIS must allocate memory to satisfy the request. This amount must be
     a multiple of the value defined by MEMORY_ALLOCATION_ALIGNMENT.


### -param PoolTag [in]

A kernel pool tag that NDIS uses to allocate the memory for the NET_BUFFER_LIST_CONTEXT structure,
     if allocation is required. The tag is a string, delimited by single quotation marks, with up to four
     characters, usually specified in reversed order. The kernel pool tag helps NDIS to identify the owner of
     the memory.


## -returns
<b>NdisAllocateNetBufferListContext</b> returns one of the following:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><b>NdisAllocateNetBufferListContext</b> successfully allocated context space either by reducing the
       value of the 
       <b>Offset</b> member of the NET_BUFFER_LIST_CONTEXT structure or by allocating new memory.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl><b>NdisAllocateNetBufferListContext</b> failed due to insufficient resources.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl><b>NdisAllocateNetBufferListContext</b> failed for reasons other than insufficient resources.

 


## -remarks
If there is enough unused context space available in the 
    <a href="netvista.net_buffer_list_context">NET_BUFFER_LIST_CONTEXT</a> structure to
    satisfy the request, 
    <b>NdisAllocateNetBufferListContext</b> simply reduces the value of the 
    <b>Offset</b> member in the NET_BUFFER_LIST_CONTEXT structure. Otherwise, NDIS allocates new memory for
    context space. You can specify 
    <i>ContextBackFill</i> to allocate extra memory so that the next call to 
    <b>NdisAllocateNetBufferListContext</b> does not have to allocate memory.

Call the 
    <a href="netvista.ndisfreenetbufferlistcontext">
    NdisFreeNetBufferListContext</a> function to release the context space in the NET_BUFFER_LIST_CONTEXT
    structure that was allocated with 
    <b>NdisAllocateNetBufferListContext</b>.


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
<a href="netvista.ndisfreenetbufferlistcontext">NdisFreeNetBufferListContext</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="netvista.net_buffer_list_context">NET_BUFFER_LIST_CONTEXT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAllocateNetBufferListContext function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

