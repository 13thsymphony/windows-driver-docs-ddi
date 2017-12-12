---
UID: NF.ndis.NdisAllocateNetBufferPool
title: NdisAllocateNetBufferPool function
author: windows-driver-content
description: Call the NdisAllocateNetBufferPool function to allocate a pool of NET_BUFFER structures.
old-location: netvista\ndisallocatenetbufferpool.htm
old-project: netvista
ms.assetid: bc27758a-a793-48a1-a6ab-bd193aa9c61a
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisAllocateNetBufferPool
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
req.alt-api: NdisAllocateNetBufferPool
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

# NdisAllocateNetBufferPool function



## -description
Call the
  <b>NdisAllocateNetBufferPool</b> function to allocate a pool of 
  <a href="netvista.net_buffer">NET_BUFFER</a> structures.



## -syntax

````
NDIS_HANDLE NdisAllocateNetBufferPool(
  _In_opt_ NDIS_HANDLE                 NdisHandle,
  _In_     PNET_BUFFER_POOL_PARAMETERS Parameters
);
````


## -parameters

### -param NdisHandle [in, optional]

An NDIS handle that was obtained during caller initialization.


### -param Parameters [in]

A pointer to a NET_BUFFER_POOL_PARAMETERS structure that defines the parameters for the pool. The
     structure is defined as follows:
     

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _NET_BUFFER_POOL_PARAMETERS {
  NDIS_OBJECT_HEADER  Header;
  ULONG  PoolTag;
  ULONG  DataSize;
} NET_BUFFER_POOL_PARAMETERS, *PNET_BUFFER_POOL_PARAMETERS;</pre>
</td>
</tr>
</table></span></div>
This structure includes the following members:




### -param Header

The 
       <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
       NET_BUFFER_POOL_PARAMETERS structure. Set the 
       <b>Type</b> member of the structure that 
       <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
       <b>Revision</b> member to NET_BUFFER_POOL_PARAMETERS_REVISION_1, and the 
       <b>Size</b> member to NDIS_SIZEOF_NET_BUFFER_POOL_PARAMETERS_REVISION_1.


### -param PoolTag

A kernel pool tag that the caller uses when it allocates 
       <a href="netvista.net_buffer">NET_BUFFER</a> structures from this pool. The tag
       is a string, delimited by single quotation marks, with up to four characters, usually specified in
       reverse order. The kernel pool tag helps NDIS to identify the owner of the NET_BUFFER structures that
       are allocated from this pool.


### -param DataSize

The default data size for data buffers associated with this pool. The caller must set this value
       if it calls the 
       <a href="netvista.ndisallocatenetbuffermdlanddata">
       NdisAllocateNetBufferMdlAndData</a> function. NDIS uses this value to set the size of the data
       buffer that it allocates for the NET_BUFFER structure. If the caller does not use this feature, this
       value should be set to zero.

</dd>
</dl>

## -returns
<b>NdisAllocateNetBufferPool</b> returns a handle to the NET_BUFFER structure pool that NDIS allocates.
     If the allocation was unsuccessful, this handle is <b>NULL</b>. This handle is a required parameter in
     subsequent calls to NDIS functions that allocate and free NET_BUFFER structures from this pool.


## -remarks
Call the following functions to allocate 
    <a href="netvista.net_buffer">NET_BUFFER</a> structures from the NET_BUFFER
    structure pool.


<a href="netvista.ndisallocatenetbuffer">NdisAllocateNetBuffer</a>



<a href="netvista.ndisallocatenetbuffermdlanddata">
       NdisAllocateNetBufferMdlAndData</a>


You can call 
    <b>NdisAllocateNetBufferPool</b> and set the 
    <b>DataSize</b> value when creating a NET_BUFFER structure pool. In this case, MDL and data are
    preallocated with each NET_BUFFER structure that the caller allocates from the pool. You must call the 
    <b>NdisAllocateNetBufferMdlAndData</b> function to allocate NET_BUFFER structures from such a pool.

MDL and data buffers that are allocated with 
    <b>NdisAllocateNetBufferMdlAndData</b> should not be freed separate from the NET_BUFFER structure. Such
    structures are freed with the NET_BUFFER structure when you call the 
    <a href="netvista.ndisfreenetbuffer">NdisFreeNetBuffer</a> function.

Call the 
    <a href="netvista.ndisfreenetbufferpool">NdisFreeNetBufferPool</a> function to
    free NET_BUFFER structure pools that are created with 
    <b>NdisAllocateNetBufferPool</b>.


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
<a href="netvista.ndisallocatenetbuffer">NdisAllocateNetBuffer</a>
</dt>
<dt>
<a href="netvista.ndisallocatenetbuffermdlanddata">
   NdisAllocateNetBufferMdlAndData</a>
</dt>
<dt>
<a href="netvista.ndisfreenetbuffer">NdisFreeNetBuffer</a>
</dt>
<dt>
<a href="netvista.ndisfreenetbufferpool">NdisFreeNetBufferPool</a>
</dt>
<dt>
<a href="netvista.net_buffer">NET_BUFFER</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAllocateNetBufferPool function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

