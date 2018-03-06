---
UID: NS:ndis._NET_BUFFER
title: "_NET_BUFFER"
author: windows-driver-content
description: The NET_BUFFER structure specifies data that is transmitted or received over the network.
old-location: netvista\net_buffer.htm
old-project: netvista
ms.assetid: 66a725f9-ae72-41b4-8840-63c9ff89ace7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PNET_BUFFER, NET_BUFFER, NET_BUFFER structure [Network Drivers Starting with Windows Vista], PNET_BUFFER, PNET_BUFFER structure pointer [Network Drivers Starting with Windows Vista], _NET_BUFFER, ndis/NET_BUFFER, ndis/PNET_BUFFER, ndis_netbuf_structures_ref_e07734b2-9135-48a5-b3d4-f6e252a52c45.xml, netvista.net_buffer"
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
-	NET_BUFFER
product: Windows
targetos: Windows
req.typenames: NET_BUFFER, *PNET_BUFFER, NET_BUFFER, *PNET_BUFFER
---

# _NET_BUFFER structure
The NET_BUFFER structure specifies data that is transmitted or received over the network.

## Syntax
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

## Members


`ChecksumBias`

The number of bytes to skip over from the beginning of the data buffer when computing a checksum.
     This member is used by the TCP/IP protocol.

`DataPhysicalAddress`

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
      <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure that is
      associated with the NET_BUFFER.

<div class="alert"><b>Note</b>  A miniport driver can set the 
      <b>DataPhysicalAddress</b> member of the NET_BUFFER structure, even if the structure is not associated
      with a split frame. In this case, 
      <b>DataPhysicalAddress</b> contains the physical address of the header MDL.</div>
<div> </div>

`MiniportReserved`

Reserved for use by miniport drivers. Miniport drivers and NDIS intermediate drivers can use this
     area for their own purposes.

`NdisPoolHandle`

A pool handle that identifies the NET_BUFFER pool from which the NET_BUFFER structure was
     allocated.

`NdisReserved`

Reserved for NDIS.

`ProtocolReserved`

Reserved for use by protocol drivers. Protocol drivers and NDIS intermediate drivers can use this
     area for their own purposes. Intermediate drivers can use this member only if it is not already in
     use.

`Reserved`

Reserved for future use.

## Remarks
NDIS drivers can call the following functions to allocate and initialize a NET_BUFFER structure:

<ul>
<li>

<a href="..\ndis\nf-ndis-ndisallocatenetbuffer.md">NdisAllocateNetBuffer</a>


</li>
<li>

<a href="..\ndis\nf-ndis-ndisallocatenetbufferandnetbufferlist.md">
       NdisAllocateNetBufferAndNetBufferList</a>


</li>
</ul>
NDIS drivers can call the 
    <a href="..\ndis\nf-ndis-ndisallocatenetbufferlistpool.md">
    NdisAllocateNetBufferListPool</a> function and then set the 
    <b>fAllocateNetBuffer</b> member of the 
    <a href="..\ndis\ns-ndis-_net_buffer_list_pool_parameters.md">NET_BUFFER_LIST_POOL_PARAMETERS</a> structure to <b>TRUE</b> when allocating a 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure pool. In this
    case, a NET_BUFFER structure is preallocated with each NET_BUFFER_LIST structure that the driver
    allocates from the pool.

Chained to each NET_BUFFER structure are one or more buffer descriptors that map buffers that contain
    network packet data. These buffer descriptors are specified as an MDL chain in the 
    <b>NetBufferHeader</b> member. Such network packet data either was received or will be transmitted.

To access additional data space in the MDL chain, NDIS drivers can call the following functions:

<ul>
<li>

<a href="..\ndis\nf-ndis-ndisretreatnetbufferdatastart.md">
       NdisRetreatNetBufferDataStart</a>


</li>
<li>

<a href="..\ndis\nf-ndis-ndisretreatnetbufferlistdatastart.md">
       NdisRetreatNetBufferListDataStart</a>


</li>
</ul>
NDIS drivers typically use the 
    <b>MiniportReserved</b> or 
    <b>ProtocolReserved</b> members of the NET_BUFFER structure to maintain NET_BUFFER structure context
    information.

<div class="alert"><b>Note</b>  Only one driver can use 
    <b>MiniportReserved</b> or 
    <b>ProtocolReserved</b> members. Therefore, if another driver has used either of these members, an
    intermediate driver cannot use them.</div>
<div> </div>
To access members of the NET_BUFFER structure, use the following macros and functions:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff568416">NET_BUFFER_NEXT_NB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568386">NET_BUFFER_FIRST_MDL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568383">NET_BUFFER_DATA_OFFSET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568382">NET_BUFFER_DATA_LENGTH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568417">NET_BUFFER_PROTOCOL_RESERVED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568415">NET_BUFFER_MINIPORT_RESERVED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568378">NET_BUFFER_CHECKSUM_BIAS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568379">NET_BUFFER_CURRENT_MDL</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568380">
       NET_BUFFER_CURRENT_MDL_OFFSET</a>



<a href="..\ndis\nf-ndis-ndisgetpoolfromnetbuffer.md">NdisGetPoolFromNetBuffer</a>


For more information on how to use net buffers, see 
    <a href="https://msdn.microsoft.com/97cddcd1-7242-4cc5-9af9-fe82a2ef995f">NET_BUFFER Architecture</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later. Supported in NDIS 6.0 and later. |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568380">NET_BUFFER_CURRENT_MDL_OFFSET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568415">NET_BUFFER_MINIPORT_RESERVED</a>



<a href="..\wdm\ns-wdm-_scatter_gather_list.md">SCATTER_GATHER_LIST</a>



<a href="..\ndis\nf-ndis-ndisallocatenetbuffer.md">NdisAllocateNetBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568383">NET_BUFFER_DATA_OFFSET</a>



<a href="..\ndis\ns-ndis-_net_buffer_list_pool_parameters.md">NET_BUFFER_LIST_POOL_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568386">NET_BUFFER_FIRST_MDL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568378">NET_BUFFER_CHECKSUM_BIAS</a>



<a href="..\ndis\nf-ndis-ndisretreatnetbufferlistdatastart.md">
   NdisRetreatNetBufferListDataStart</a>



<a href="..\ndis\nf-ndis-ndisallocatenetbufferandnetbufferlist.md">
   NdisAllocateNetBufferAndNetBufferList</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\ndis\nf-ndis-ndismsendnetbufferlistscomplete.md">
   NdisMSendNetBufferListsComplete</a>



<a href="..\ndis\nf-ndis-ndisretreatnetbufferdatastart.md">
   NdisRetreatNetBufferDataStart</a>



<a href="..\ndis\nf-ndis-ndisgetpoolfromnetbuffer.md">NdisGetPoolFromNetBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568416">NET_BUFFER_NEXT_NB</a>



<a href="..\ndis\ns-ndis-_net_buffer_header.md">NET_BUFFER_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568382">NET_BUFFER_DATA_LENGTH</a>



<a href="..\ndis\nf-ndis-ndisallocatenetbufferlistpool.md">
   NdisAllocateNetBufferListPool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568379">NET_BUFFER_CURRENT_MDL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568417">NET_BUFFER_PROTOCOL_RESERVED</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NET_BUFFER structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>