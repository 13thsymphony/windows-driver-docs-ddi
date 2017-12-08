---
UID: NS.NDIS._NET_BUFFER~R1
title: _NET_BUFFER
author: windows-driver-content
description: The NET_BUFFER structure specifies data that is transmitted or received over the network.
old-location: netvista\net_buffer.htm
old-project: netvista
ms.assetid: 66a725f9-ae72-41b4-8840-63c9ff89ace7
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _NET_BUFFER, NET_BUFFER, *PNET_BUFFER
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
req.alt-api: NET_BUFFER
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

# _NET_BUFFER structure



## -description
The NET_BUFFER structure specifies data that is transmitted or received over the network.


## -syntax

````
typedef struct _NET_BUFFER {
  NET_BUFFER_HEADER     NetBufferHeader;
  USHORT                ChecksumBias;
  USHORT                Reserved;
  NDIS_HANDLE           NdisPoolHandle;
  PVOID                 NdisReserved[2];
  PVOID                 ProtocolReserved[6];
  PVOID                 MiniportReserved[4];
  NDIS_PHYSICAL_ADDRESS DataPhysicalAddress;
#if (NDIS_SUPPORT_NDIS620)
  union {
    PNET_BUFFER_SHARED_MEMORY SharedMemoryInfo;
    PSCATTER_GATHER_LIST      ScatterGatherList;
  };
#endif 
} NET_BUFFER, *PNET_BUFFER;
````


## -struct-fields

### -field NetBufferHeader

A 
     <a href="netvista.net_buffer_header">NET_BUFFER_HEADER</a> structure.

### -field ChecksumBias

The number of bytes to skip over from the beginning of the data buffer when computing a checksum.
     This member is used by the TCP/IP protocol.

### -field Reserved

Reserved for future use.

### -field NdisPoolHandle

A pool handle that identifies the NET_BUFFER pool from which the NET_BUFFER structure was
     allocated.

### -field NdisReserved

Reserved for NDIS.

### -field ProtocolReserved

Reserved for use by protocol drivers. Protocol drivers and NDIS intermediate drivers can use this
     area for their own purposes. Intermediate drivers can use this member only if it is not already in
     use.

### -field MiniportReserved

Reserved for use by miniport drivers. Miniport drivers and NDIS intermediate drivers can use this
     area for their own purposes.

### -field DataPhysicalAddress

<div class="alert"><b>Note</b>  The name of this member is 
      <b>NdisReserved1</b> for NDIS 6.0 drivers and is 
      <b>DataPhysicalAddress</b> for NDIS 6.1 and later drivers. For NDIS 6.0 drivers, this member is reserved
      for NDIS.</div>
<div> </div>
The physical address of the data portion of a frame. This member should be to zero if the driver
      that allocated NET_BUFFER does not specify the address. This member is valid only if the
      NDIS_NBL_FLAGS_SPLIT_AT_UPPER_LAYER_PROTOCOL_HEADER or
      NDIS_NBL_FLAGS_SPLIT_AT_UPPER_LAYER_PROTOCOL_PAYLOAD flag is set in the 
      <b>NblFlags</b> member of the 
      <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure that is
      associated with the NET_BUFFER.
<div class="alert"><b>Note</b>  A miniport driver can set the 
      <b>DataPhysicalAddress</b> member of the NET_BUFFER structure, even if the structure is not associated
      with a split frame. In this case, 
      <b>DataPhysicalAddress</b> contains the physical address of the header MDL.</div>
<div> </div>

### -field SharedMemoryInfo

A pointer to an 
      <a href="netvista.net_buffer_shared_memory">
      NET_BUFFER_SHARED_MEMORY</a> structure.

### -field ScatterGatherList

The SCATTER_GATHER_LIST structure describes a scatter/gather list for DMA.

## -remarks
NDIS drivers can call the following functions to allocate and initialize a NET_BUFFER structure:


<a href="netvista.ndisallocatenetbuffer">NdisAllocateNetBuffer</a>



<a href="netvista.ndisallocatenetbufferandnetbufferlist">
       NdisAllocateNetBufferAndNetBufferList</a>


NDIS drivers can call the 
    <a href="netvista.ndisallocatenetbufferlistpool">
    NdisAllocateNetBufferListPool</a> function and then set the 
    <b>fAllocateNetBuffer</b> member of the 
    <a href="netvista.net_buffer_list_pool_parameters">NET_BUFFER_LIST_POOL_PARAMETERS</a> structure to <b>TRUE</b> when allocating a 
    <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure pool. In this
    case, a NET_BUFFER structure is preallocated with each NET_BUFFER_LIST structure that the driver
    allocates from the pool.

Chained to each NET_BUFFER structure are one or more buffer descriptors that map buffers that contain
    network packet data. These buffer descriptors are specified as an MDL chain in the 
    <b>NetBufferHeader</b> member. Such network packet data either was received or will be transmitted.

To access additional data space in the MDL chain, NDIS drivers can call the following functions:


<a href="netvista.ndisretreatnetbufferdatastart">
       NdisRetreatNetBufferDataStart</a>



<a href="netvista.ndisretreatnetbufferlistdatastart">
       NdisRetreatNetBufferListDataStart</a>


NDIS drivers typically use the 
    <b>MiniportReserved</b> or 
    <b>ProtocolReserved</b> members of the NET_BUFFER structure to maintain NET_BUFFER structure context
    information.

To access members of the NET_BUFFER structure, use the following macros and functions:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff568416">NET_BUFFER_NEXT_NB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568386">NET_BUFFER_FIRST_MDL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568383">NET_BUFFER_DATA_OFFSET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568382">NET_BUFFER_DATA_LENGTH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568417">NET_BUFFER_PROTOCOL_RESERVED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568415">NET_BUFFER_MINIPORT_RESERVED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568378">NET_BUFFER_CHECKSUM_BIAS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568379">NET_BUFFER_CURRENT_MDL</a>



<a href="netvista.net_buffer_current_mdl_offset">
       NET_BUFFER_CURRENT_MDL_OFFSET</a>



<a href="netvista.ndisgetpoolfromnetbuffer">NdisGetPoolFromNetBuffer</a>


For more information on how to use net buffers, see 
    <a href="netvista.net_buffer_architecture">NET_BUFFER Architecture</a>.

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
<a href="netvista.ndisallocatenetbuffer">NdisAllocateNetBuffer</a>
</dt>
<dt>
<a href="netvista.ndisallocatenetbufferandnetbufferlist">
   NdisAllocateNetBufferAndNetBufferList</a>
</dt>
<dt>
<a href="netvista.ndisallocatenetbufferlistpool">
   NdisAllocateNetBufferListPool</a>
</dt>
<dt>
<a href="netvista.ndisgetpoolfromnetbuffer">NdisGetPoolFromNetBuffer</a>
</dt>
<dt>
<a href="netvista.ndismsendnetbufferlistscomplete">
   NdisMSendNetBufferListsComplete</a>
</dt>
<dt>
<a href="netvista.ndisretreatnetbufferdatastart">
   NdisRetreatNetBufferDataStart</a>
</dt>
<dt>
<a href="netvista.ndisretreatnetbufferlistdatastart">
   NdisRetreatNetBufferListDataStart</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568378">NET_BUFFER_CHECKSUM_BIAS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568379">NET_BUFFER_CURRENT_MDL</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568380">NET_BUFFER_CURRENT_MDL_OFFSET</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568382">NET_BUFFER_DATA_LENGTH</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568383">NET_BUFFER_DATA_OFFSET</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568386">NET_BUFFER_FIRST_MDL</a>
</dt>
<dt>
<a href="netvista.net_buffer_header">NET_BUFFER_HEADER</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="netvista.net_buffer_list_pool_parameters">NET_BUFFER_LIST_POOL_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568415">NET_BUFFER_MINIPORT_RESERVED</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568416">NET_BUFFER_NEXT_NB</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568417">NET_BUFFER_PROTOCOL_RESERVED</a>
</dt>
<dt>
<a href="kernel.scatter_gather_list">SCATTER_GATHER_LIST</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NET_BUFFER structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
