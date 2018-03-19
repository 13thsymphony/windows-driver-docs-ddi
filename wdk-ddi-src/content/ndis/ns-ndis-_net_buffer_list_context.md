---
UID: NS:ndis._NET_BUFFER_LIST_CONTEXT
title: "_NET_BUFFER_LIST_CONTEXT"
author: windows-driver-content
description: The NET_BUFFER_LIST_CONTEXT structure stores context information for a NET_BUFFER_LIST structure.
old-location: netvista\net_buffer_list_context.htm
old-project: netvista
ms.assetid: e5d70be6-daa5-4d2e-94fd-5739edd8821e
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNET_BUFFER_LIST_CONTEXT, NET_BUFFER_LIST_CONTEXT, NET_BUFFER_LIST_CONTEXT structure [Network Drivers Starting with Windows Vista], PNET_BUFFER_LIST_CONTEXT, PNET_BUFFER_LIST_CONTEXT structure pointer [Network Drivers Starting with Windows Vista], _NET_BUFFER_LIST_CONTEXT, ndis/NET_BUFFER_LIST_CONTEXT, ndis/PNET_BUFFER_LIST_CONTEXT, ndis_netbuf_structures_ref_8f7ae065-a4d5-4fc9-92f1-36e25e19bac2.xml, netvista.net_buffer_list_context"
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NET_BUFFER_LIST_CONTEXT
product: Windows
targetos: Windows
req.typenames: NET_BUFFER_LIST_CONTEXT, *PNET_BUFFER_LIST_CONTEXT, NET_BUFFER_LIST_CONTEXT, *PNET_BUFFER_LIST_CONTEXT
---

# _NET_BUFFER_LIST_CONTEXT structure
The NET_BUFFER_LIST_CONTEXT structure stores context information for a 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.

## Syntax
````
typedef struct _NET_BUFFER_LIST_CONTEXT {
  PNET_BUFFER_LIST_CONTEXT Next;
  USHORT                   Size;
  USHORT                   Offset;
  UCHAR                    ContextData[];
} NET_BUFFER_LIST_CONTEXT, *PNET_BUFFER_LIST_CONTEXT;
````

## Members


`Next`

A pointer to the next NET_BUFFER_LIST_CONTEXT structure in a linked list of
     NET_BUFFER_LIST_CONTEXT structures.

`Size`

The size, in bytes, of the entire context space in the NET_BUFFER_LIST_CONTEXT structure,
     including the used and unused context space.

`Offset`

The offset, in bytes, from the beginning of the context data buffer to the start of the context
     data in the NET_BUFFER_LIST_CONTEXT structure. The 
     <b>Offset</b> member also specifies the size in bytes of the unused context space in the
     NET_BUFFER_LIST_CONTEXT structure.

`ContextData`

The context data buffer. The context data can include any information that a driver
     requires.

## Remarks
Every 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure can include a
    preallocated NET_BUFFER_LIST_CONTEXT structure. As a NET_BUFFER_LIST structure travels through the driver
    stack, the linked list of NET_BUFFER_LIST_CONTEXT structures can expand to accommodate additional data
    space for each driver.

Drivers should use the following NDIS macros and functions to access and manipulate members in a
    NET_BUFFER_LIST_CONTEXT structure:

<ul>
<li>

<a href="..\ndis\nf-ndis-ndisallocatenetbufferlistcontext.md">
       NdisAllocateNetBufferListContext</a>


</li>
<li>

<a href="..\ndis\nf-ndis-ndisfreenetbufferlistcontext.md">
       NdisFreeNetBufferListContext</a>


</li>
<li>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568391">
       NET_BUFFER_LIST_CONTEXT_DATA_START</a>


</li>
<li>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568390">
       NET_BUFFER_LIST_CONTEXT_DATA_SIZE</a>


</li>
</ul>
The 
    <b>ContextData</b> member of the NET_BUFFER_LIST_CONTEXT structure specifies the data portion of the
    NET_BUFFER_LIST_CONTEXT structure. To improve system performance, a driver should preallocate any
    required context data space when the driver allocates a NET_BUFFER_LIST structure pool. To preallocate
    this data space, a driver calls the 
    <a href="..\ndis\nf-ndis-ndisallocatenetbufferlistpool.md">
    NdisAllocateNetBufferListPool</a> function and then specifies the amount of data space required in the 
    <i>ContextSize</i> parameter. Preallocation of this data space saves NDIS from allocating memory in the
    receive and send paths.

<div class="alert"><b>Note</b>  NDIS estimates the required context data space and, if necessary, adjusts the
    allocated data space to meet the requirements for the entire driver stack.</div>
<div> </div>
The 
    <b>Offset</b> member specifies the amount of unused context space in the NET_BUFFER_LIST_CONTEXT
    structure. The 
    <b>Offset</b> member also indicates the offset from the beginning of the 
    <b>ContextData</b> member to the start of the used context data space.

NDIS drivers call the 
    <a href="..\ndis\nf-ndis-ndisallocatenetbufferlistcontext.md">
    NdisAllocateNetBufferListContext</a> function to allocate contiguous buffer space in the
    NET_BUFFER_LIST_CONTEXT structure. If necessary, NDIS allocates a new NET_BUFFER_LIST_CONTEXT structure
    with additional space to honor the request. NDIS drivers call the 
    <a href="..\ndis\nf-ndis-ndisfreenetbufferlistcontext.md">
    NdisFreeNetBufferListContext</a> function to free the buffer space.

Use the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568390">
    NET_BUFFER_LIST_CONTEXT_DATA_SIZE</a> macro to obtain the size of the used context space. Use the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568391">
    NET_BUFFER_LIST_CONTEXT_DATA_START</a> macro to get the starting address of the used context space.

For more information on how to use net buffers, see 
    <a href="https://msdn.microsoft.com/97cddcd1-7242-4cc5-9af9-fe82a2ef995f">NET_BUFFER Architecture</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later. Supported in NDIS 6.0 and later. |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568390">
   NET_BUFFER_LIST_CONTEXT_DATA_SIZE</a>



<a href="..\ndis\nf-ndis-ndisallocatenetbufferlistpool.md">
   NdisAllocateNetBufferListPool</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568391">
   NET_BUFFER_LIST_CONTEXT_DATA_START</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\ndis\nf-ndis-ndisfreenetbufferlistcontext.md">NdisFreeNetBufferListContext</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



<a href="..\ndis\nf-ndis-ndisallocatenetbufferlistcontext.md">
   NdisAllocateNetBufferListContext</a>