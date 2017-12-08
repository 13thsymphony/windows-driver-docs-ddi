---
UID: NS.NDIS._NET_BUFFER_LIST_POOL_PARAMETERS
title: _NET_BUFFER_LIST_POOL_PARAMETERS
author: windows-driver-content
description: The NET_BUFFER_LIST_POOL_PARAMETERS structure defines the parameters for a pool of NET_BUFFER_LIST structures.
old-location: netvista\net_buffer_list_pool_parameters.htm
old-project: netvista
ms.assetid: DBB172A0-957E-4FAC-9727-D72B060E3193
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _NET_BUFFER_LIST_POOL_PARAMETERS, NET_BUFFER_LIST_POOL_PARAMETERS, *PNET_BUFFER_LIST_POOL_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NET_BUFFER_LIST_POOL_PARAMETERS
req.alt-loc: ndis.h
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
---

# _NET_BUFFER_LIST_POOL_PARAMETERS structure



## -description

The <b>NET_BUFFER_LIST_POOL_PARAMETERS</b> structure defines the parameters for a pool of <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures.

The <b>NET_BUFFER_LIST_POOL_PARAMETERS</b> structure defines the parameters for a pool of <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures.


## -syntax

````
typedef struct _NET_BUFFER_LIST_POOL_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  UCHAR              ProtocolId;
  BOOLEAN            fAllocateNetBuffer;
  USHORT             ContextSize;
  ULONG              PoolTag;
  ULONG              DataSize;
} NET_BUFFER_LIST_POOL_PARAMETERS, *PNET_BUFFER_LIST_POOL_PARAMETERS;
````


## -struct-fields

### -field Header

The type, revision, and size of the <b>NET_BUFFER_LIST_POOL_PARAMETERS</b> structure. This member is formatted as an <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure.
The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NET_BUFFER_LIST_POOL_PARAMETERS</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 


### -field NET_BUFFER_LIST_POOL_PARAMETERS_REVISION_1

Original version for NDIS 6.0.
Set the <b>Size</b> member to NDIS_SIZEOF_NET_BUFFER_LIST_POOL_PARAMETERS_REVISION_1.
</dd>
</dl>

### -field ProtocolId

The type of caller. Miniport, filter, and intermediate drivers set this field to zero
       (NDIS_PROTOCOL_ID_DEFAULT). Protocol drivers use one of the following values:
       


### -field NDIS_PROTOCOL_ID_DEFAULT

Specifies a default protocol driver identifier.

### -field NDIS_PROTOCOL_ID_TCP_IP

Specifies the TCP/IP protocol.

### -field NDIS_PROTOCOL_ID_IPX

Specifies the IPX protocol.

### -field NDIS_PROTOCOL_ID_NBF

Specifies the NetBEUI protocol.
</dd>
</dl>

### -field fAllocateNetBuffer

If this member is set to TRUE, NDIS allocates a pool of <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures. Each allocated <b>NET_BUFFER_LIST</b> structure is initialized with one 
       <a href="netvista.net_buffer">NET_BUFFER</a> structure. 
If this member is set to FALSE, NDIS allocates a pool of <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures. Each allocated <b>NET_BUFFER_LIST</b> structure is not initialized  to contain any 
       <a href="netvista.net_buffer">NET_BUFFER</a> structures.
For more information, see the Remarks section.

### -field ContextSize

The size, in bytes, of the preallocated 
       <a href="netvista.net_buffer_list_context">NET_BUFFER_LIST_CONTEXT</a> structure
       data that NDIS should provide for the NET_BUFFER_LIST structures in this pool. The 
       <b>ContextSize</b> must be a multiple of the value that is defined by MEMORY_ALLOCATION_ALIGNMENT.

### -field PoolTag

A kernel pool tag that the caller uses when it allocates NET_BUFFER_LIST structures from this
       pool. The tag is a string, delimited by single quotation marks, with up to four characters, usually
       specified in reversed order. The kernel pool tag helps NDIS to identify the owner of the
       <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures that are allocated from this pool.

### -field DataSize

The default data size, in bytes, for data buffers that are associated with this 
       <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> pool, if any. NDIS uses
       this value to set the size of any data buffers that it allocates for any associated 
       <a href="netvista.net_buffer">NET_BUFFER</a> structures. 
       
For more information, see the Remarks section.

## -remarks
If 
       <b>fAllocateNetBuffer</b> is set to FALSE, NDIS will not allocate <a href="netvista.net_buffer">NET_BUFFER</a> structures, and 
       <b>DataSize</b> should be set to zero.

If 
       <b>DataSize</b> is not zero, 
       <b>fAllocateNetBuffer</b> must be set to TRUE. This causes NDIS to allocate the <a href="netvista.net_buffer">NET_BUFFER</a> structure with a data buffer
       of the specified size.

If 
       <b>DataSize</b> is zero and 
       <b>fAllocateNetBuffer</b> is <b>TRUE</b>, NDIS allocates the <a href="netvista.net_buffer">NET_BUFFER</a> structure but not the data
       buffer.

The <i>Parameters</i> parameter of the <a href="netvista.ndisallocatenetbufferlistpool">NdisAllocateNetBufferListPool</a> function contains a pointer to an <b>NET_BUFFER_LIST_POOL_PARAMETERS</b> structure.

## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndisallocatenetbufferlistpool">NdisAllocateNetBufferListPool</a>
</dt>
<dt>
<a href="netvista.net_buffer">NET_BUFFER</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="netvista.net_buffer_list_data">NET_BUFFER_LIST_DATA</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NET_BUFFER_LIST_POOL_PARAMETERS structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
