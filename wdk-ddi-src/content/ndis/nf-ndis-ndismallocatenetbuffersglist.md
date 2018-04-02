---
UID: NF:ndis.NdisMAllocateNetBufferSGList
title: NdisMAllocateNetBufferSGList function
author: windows-driver-content
description: Bus-master miniport drivers call the NdisMAllocateNetBufferSGList function to obtain a scatter/gather list for the network data that is associated with a NET_BUFFER structure.
old-location: netvista\ndismallocatenetbuffersglist.htm
old-project: netvista
ms.assetid: 3fd8d121-a249-433a-a93d-4027a4bfcb61
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisMAllocateNetBufferSGList, NdisMAllocateNetBufferSGList function [Network Drivers Starting with Windows Vista], ndis/NdisMAllocateNetBufferSGList, ndis_sgdma_ref_7d06207d-de5d-41a8-b6e8-4ecab32123a1.xml, netvista.ndismallocatenetbuffersglist
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
req.ddi-compliance: Irql_Gather_DMA_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMAllocateNetBufferSGList
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisMAllocateNetBufferSGList function
Bus-master miniport drivers call the 
  <b>NdisMAllocateNetBufferSGList</b> function to obtain a scatter/gather list for the network data that is
  associated with a 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure.

## Syntax

```
NDIS_STATUS NdisMAllocateNetBufferSGList(
  NDIS_HANDLE NdisMiniportDmaHandle,
  PNET_BUFFER NetBuffer,
  PVOID       Context,
  ULONG       Flags,
  PVOID       ScatterGatherListBuffer,
  ULONG       ScatterGatherListBufferSize
);
```

## Parameters

`NdisMiniportDmaHandle`

A handle to a context area that NDIS uses to manage a DMA resource. The caller obtained this
     handle by calling the 
     <a href="https://msdn.microsoft.com/90ce64a2-9140-4b5f-88aa-b4f01a3d0c6f">
     NdisMRegisterScatterGatherDma</a> function.

`NetBuffer`

A pointer to a NET_BUFFER structure. 
     <b>NdisMAllocateNetBufferSGList</b> allocates a scatter/gather list for the network data that is
     associated with this NET_BUFFER structure. The scatter/gather list is generated from the data starting
     at the beginning of the MDL that is specified at the 
     <b>CurrentMdl</b> member of the associated 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568381">NET_BUFFER_DATA</a> structure.

`Context`

A pointer to a context area that the caller created. HAL passes this pointer to 
     <a href="https://msdn.microsoft.com/ddd5d14f-f886-40d0-9fc8-eeb37da63ebd">MiniportProcessSGList</a> after HAL
     creates the scatter/gather list. The caller can use this context area for its own purposes.

`Flags`

NDIS flags that can be combined with an OR operation. To clear all the flags, set this member to
     zero. This function supports the NDIS_SG_LIST_WRITE_TO_DEVICE flag which; if set, indicates the
     direction of the DMA transfer is from the NET_BUFFER to the device. If NDIS_SG_LIST_WRITE_TO_DEVICE is
     clear, the transfer is from the device. Miniport drivers should set this flag on the send path when DMA
     operation transfers data from a NET_BUFFER to the device. Miniport drivers that perform DMA operations
     from the device to a pre-allocated NET_BUFFER, for example chimney offload capable NICs during receive
     operations, should clear this flag.

`ScatterGatherListBuffer`

If not <b>NULL</b>, 
     <i>ScatterGatherListBuffer</i> specifies a pointer to storage that the caller allocates to hold the
     scatter/gather list. If <b>NULL</b>, NDIS allocates storage for the scatter/gather list.

`ScatterGatherListBufferSize`

If the 
     <i>ScatterGatherListBuffer</i> parameter is not <b>NULL</b>, 
     <i>ScatterGatherListBufferSize</i> specifies the size of the buffer that contains the scatter/gather
     list. If this size is too small, NDIS allocates storage for the scatter/gather list. If the 
     <i>ScatterGatherListBuffer</i> parameter is <b>NULL</b>, this parameter is not used.


## Return Value

<b>NdisMAllocateNetBufferSGList</b> returns one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisMAllocateNetBufferSGList</b> successfully built the scatter/gather list for the specified
       NET_BUFFER structure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisMAllocateNetBufferSGList</b> failed due to insufficient resources.

</td>
</tr>
</table>

## Remarks

An NDIS bus-master miniport driver calls 
    <b>NdisMAllocateNetBufferSGList</b> from its 
    <a href="https://msdn.microsoft.com/0bd5966d-66a6-4548-8c84-7cedced2cf40">
    MiniportSendNetBufferLists</a> function. The miniport driver calls 
    <b>NdisMAllocateNetBufferSGList</b> once for each 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure for which it must obtain a
    scatter/gather list.

When a miniport driver calls 
    <b>NdisMAllocateNetBufferSGList</b>, NDIS calls HAL to build the scatter/gather list. After HAL builds
    the scatter/gather list, it calls the 
    <i>MiniportProcessSGList</i> function that the miniport driver registered by calling 
    <a href="https://msdn.microsoft.com/90ce64a2-9140-4b5f-88aa-b4f01a3d0c6f">
    NdisMRegisterScatterGatherDma</a>.

HAL can call 
    <i>MiniportProcessSGList</i> before or after NDIS returns from 
    <b>NdisMAllocateNetBufferSGList</b>. Miniport drivers must not attempt to access the scatter/gather list
    until after HAL calls 
    <i>MiniportProcessSGList</i>.

To improve system performance, miniport drivers should preallocate buffers for the use in the 
    <i>ScatterGatherListBuffer</i> parameter of 
    <b>NdisMAllocateNetBufferSGList</b>. NDIS provides the recommended size for the buffers in the 
    <b>ScatterGatherListSize</b> member of the 
    <i>DmaDescription</i> parameter when the miniport driver calls 
    <b>NdisMRegisterScatterGatherDma</b>. Miniport drivers specify the size of the buffer in the 
    <i>ScatterGatherListBufferSize</i> parameter when they call 
    <b>NdisMAllocateNetBufferSGList</b>.

NDIS might allocate a buffer even if the miniport driver specifies a buffer in the 
    <i>ScatterGatherListBuffer</i> parameter. This can happen if the specified buffer is too small to hold the
    scatter/gather list. Therefore, driver writers must not assume that the buffer specified in the 
    <i>ScatterGatherListBuffer</i> parameter contains the scatter/gather list. HAL passes the correct
    scatter/gather list pointer to the miniport driver's 
    <i>MiniportProcessSGList</i> function.

To improve system performance, the scatter/gather list is generated from the network data starting at
    the beginning of the MDL that is specified at the 
    <b>CurrentMdl</b> member of the associated 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568381">NET_BUFFER_DATA</a> structure. The start of the
    network data in the SG list is offset from the beginning of the SG list by the value specified in the 
    <b>CurrentMdlOffset</b> member of the associated NET_BUFFER_DATA structure.

Miniport drivers must call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff563586">NdisMFreeNetBufferSGList</a> function
    to free a scatter/gather list.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | DISPATCH_LEVEL |
| **DDI compliance rules** | Irql_Gather_DMA_Function |

## See Also

<a href="https://msdn.microsoft.com/95463617-65df-4c02-82f4-e3aba44d42fb">Allocating and Freeing Scatter/Gather Lists</a>



<a href="https://msdn.microsoft.com/c7e702aa-494f-4b27-a7c3-d42ef8f42a6e">Miniport Driver Scatter/Gather DMA</a>



<a href="https://msdn.microsoft.com/ddd5d14f-f886-40d0-9fc8-eeb37da63ebd">MiniportProcessSGList</a>



<a href="https://msdn.microsoft.com/0bd5966d-66a6-4548-8c84-7cedced2cf40">MiniportSendNetBufferLists</a>



<a href="https://msdn.microsoft.com/70b8321b-7b21-4d11-a9c2-46b0caa26ce6">NDIS Scatter/Gather DMA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568381">NET_BUFFER_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563586">NdisMFreeNetBufferSGList</a>



<a href="https://msdn.microsoft.com/90ce64a2-9140-4b5f-88aa-b4f01a3d0c6f">
   NdisMRegisterScatterGatherDma</a>



<a href="https://msdn.microsoft.com/b24e0a56-1864-4f70-a646-c35e8eccd9e3">Registering and Deregistering DMA Channels</a>