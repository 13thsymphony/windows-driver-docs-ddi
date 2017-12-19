---
UID: NF.ndis.NdisMRegisterScatterGatherDma
title: NdisMRegisterScatterGatherDma function
author: windows-driver-content
description: Bus master miniport drivers call the NdisMRegisterScatterGatherDma function from MiniportInitializeEx to initialize a scatter/gather DMA channel.
old-location: netvista\ndismregisterscattergatherdma.htm
old-project: NetVista
ms.assetid: 90ce64a2-9140-4b5f-88aa-b4f01a3d0c6f
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisMRegisterScatterGatherDma
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
req.alt-api: NdisMRegisterScatterGatherDma
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Init_RegisterSG, Irql_Gather_DMA_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# NdisMRegisterScatterGatherDma function



## -description
Bus master miniport drivers call the 
  <b>NdisMRegisterScatterGatherDma</b> function from 
  <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> to initialize a
  scatter/gather DMA channel.



## -syntax

````
NDIS_STATUS NdisMRegisterScatterGatherDma(
  _In_    NDIS_HANDLE              MiniportAdapterHandle,
  _Inout_ PNDIS_SG_DMA_DESCRIPTION DmaDescription,
  _Out_   PNDIS_HANDLE             NdisMiniportDmaHandle
);
````


## -parameters

### -param MiniportAdapterHandle [in]

The miniport handle that NDIS passed to 
     <i>MiniportInitializeEx</i>.


### -param DmaDescription [in, out]

A pointer to an NDIS_SG_DMA_DESCRIPTION structure. This structure describes the scatter/gather DMA
     properties of the miniport driver. The structure is defined as follows:
     

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _NDIS_SG_DMA_DESCRIPTION {
  NDIS_OBJECT_HEADER  Header;
  ULONG  Flags;
  ULONG  MaximumPhysicalMapping;
  MINIPORT_PROCESS_SG_LIST_HANDLER  ProcessSGListHandler;
  MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE_HANDLER  SharedMemAllocateCompleteHandler;
  ULONG  ScatterGatherListSize;
} NDIS_SG_DMA_DESCRIPTION, *PNDIS_SG_DMA_DESCRIPTION;
 </pre>
</td>
</tr>
</table></span></div>
This structure includes the following members:




### -param Header

The 
       <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
       NDIS_SG_DMA_DESCRIPTION structure. Set the 
       <b>Type</b> member of the structure that 
       <b>Header</b> specifies to NDIS_OBJECT_TYPE_SG_DMA_DESCRIPTION, the 
       <b>Revision</b> member to NDIS_SG_DMA_DESCRIPTION_REVISION_1, and the 
       <b>Size</b> member to NDIS_SIZEOF_SG_DMA_DESCRIPTION_REVISION_1.


### -param Flags

A set of bit flags that define scatter/gather characteristics. Set this member to the bitwise OR
       of all the required flags. 
       

The NDIS_SG_DMA_64_BIT_ADDRESS flag specifies that the NIC can use 64-bit addressing for DMA
       operations. Otherwise, the NIC uses 32-bit addressing.

Set this member to zero if 64-bit addressing is not required.


### -param MaximumPhysicalMapping

The maximum number of bytes that the NIC can transfer in a single DMA operation. NDIS provides
       this value to the hardware abstraction layer (HAL) when allocating a DMA channel, and HAL uses this
       value to determine the maximum number of map registers to reserve for the NIC.


### -param ProcessSGListHandler

The 
       <a href="..\ndis\nc-ndis-miniport_process_sg_list.md">MiniportProcessSGList</a> function
       that NDIS calls when HAL is done building the scatter/gather list.


### -param SharedMemAllocateCompleteHandler

The 
       <a href="..\ndis\nc-ndis-miniport_allocate_shared_mem_complete.md">
       MiniportSharedMemoryAllocateComplete</a> function for miniport drivers that call 
       <a href="netvista.ndismallocatesharedmemoryasyncex">
       NdisMAllocateSharedMemoryAsyncEx</a>. This field is optional and it should be <b>NULL</b> if the miniport
       driver does not call 
       <b>NdisMAllocateSharedMemoryAsyncEx</b>.


### -param ScatterGatherListSize

The size, in bytes, of the memory that is required to hold a scatter/gather list. NDIS sets this
       value before it returns from 
       <b>NdisMRegisterScatterGatherDma</b>. Miniport drivers should use this size to preallocate memory for
       each scatter/gather list.

</dd>
</dl>

### -param NdisMiniportDmaHandle [out]

A pointer to a variable that the caller supplies and that NDIS fills with a handle. The handle
     identifies a context area that NDIS uses to manage this DMA resource. The miniport driver passes this
     handle to NDIS in subsequent calls to NDIS that involve this DMA resource.


## -returns
<b>NdisMRegisterScatterGatherDma</b> returns one of the following:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><b>NdisMRegisterScatterGatherDma</b> successfully allocated resources for bus-master DMA
       operations.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl><b>NdisMRegisterScatterGatherDma</b> failed due to insufficient resources.
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED</b></dt>
</dl><b>NdisMRegisterScatterGatherDma</b> failed because the miniport did not specify that it supports NDIS
       6.0 or later versions, or because the miniport driver did not specify that its NIC is a bus-master DMA
       device. A miniport driver specifies its NDIS version when it calls 
       <a href="netvista.ndismregisterminiportdriver">
       NdisMRegisterMiniportDriver</a>. A miniport driver specifies that it supports bus-master DMA
       devices when it calls 
       <a href="netvista.ndismsetminiportattributes">
       NdisMSetMiniportAttributes</a>.
<dl>
<dt><b>NDIS_STATUS_BAD_VERSION</b></dt>
</dl>The current version of NDIS does not support the version specified in the 
       <b>Revision</b> member of the 
       <b>Header</b> structure of 
       <i>DmaDescription</i> .

 


## -remarks
An NDIS bus-master miniport driver calls 
    <b>NdisMRegisterScatterGatherDma</b> within its 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function to
    initialize resources for scatter/gather DMA operations. The 
    <i>DmaDescription</i> parameter that the miniport driver passes to 
    <b>NdisMRegisterScatterGatherDma</b> contains the information that NDIS uses to initialize the
    scatter/gather DMA resources. After 
    <b>NdisMRegisterScatterGatherDma</b> returns, the 
    <b>ScatterGatherListSize</b> member of 
    <i>DmaDescription</i> contains a buffer size that should be sufficient to hold a scatter/gather list.
    Miniport drivers should use this size to preallocate the memory for scatter/gather lists.

The 
    <b>ProcessSGListHandler</b> member in the 
    <i>DmaDescription</i> parameter defines the entry point in the miniport driver for the 
    <a href="..\ndis\nc-ndis-miniport_process_sg_list.md">MiniportProcessSGList</a> function.
    When a miniport driver calls 
    <a href="netvista.ndismallocatenetbuffersglist">
    NdisMAllocateNetBufferSGList</a>, NDIS calls HAL to provide the scatter/gather list to the miniport
    driver. HAL calls 
    <i>MiniportProcessSGList</i> after HAL finishes building the scatter/gather list. NDIS can call 
    <i>MiniportProcessSGList</i> outside the context of the call to 
    <b>NdisMAllocateNetBufferSGList</b>.

<b>NdisMRegisterScatterGatherDma</b> returns a pointer to a context area that is opaque to the miniport
    driver. The miniport driver must use this handle in subsequent calls to NDIS scatter/gather DMA
    functions.

Bus-master miniport drivers call 
    <a href="netvista.ndismallocatesharedmemoryasyncex">
    NdisMAllocateSharedMemoryAsyncEx</a> to dynamically allocate shared memory for data transfer
    operations. This call is required when high network traffic causes the miniport driver to run low on the
    shared memory space that the driver allocated during initialization. If 
    <b>NdisMAllocateSharedMemoryAsyncEx</b> returns NDIS_STATUS_PENDING, NDIS calls the 
    <a href="..\ndis\nc-ndis-miniport_allocate_shared_mem_complete.md">
    MiniportSharedMemoryAllocateComplete</a> function to complete the operation at a later time. Miniport
    drivers specify the entry point for the 
    <i>MiniportSharedMemoryAllocateComplete</i> function in the 
    <b>SharedMemAllocateCompleteHandler</b> member of the 
    <i>DmaDescription</i> parameter.

Miniport drivers call the 
    <a href="netvista.ndismderegisterscattergatherdma">
    NdisMDeregisterScatterGatherDma</a> function to deallocate the DMA resources that 
    <b>NdisMRegisterScatterGatherDma</b> allocated.


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
PASSIVE_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.ndis_init_registersg">Init_RegisterSG</a>, <a href="devtest.ndis_irql_gather_dma_function">Irql_Gather_DMA_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_process_sg_list.md">MiniportProcessSGList</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_allocate_shared_mem_complete.md">
   MiniportSharedMemoryAllocateComplete</a>
</dt>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndismallocatenetbuffersglist">NdisMAllocateNetBufferSGList</a>
</dt>
<dt>
<a href="netvista.ndismallocatesharedmemoryasyncex">
   NdisMAllocateSharedMemoryAsyncEx</a>
</dt>
<dt>
<a href="netvista.ndismderegisterscattergatherdma">
   NdisMDeregisterScatterGatherDma</a>
</dt>
<dt>
<a href="netvista.ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>
</dt>
<dt>
<a href="netvista.ndismsetminiportattributes">NdisMSetMiniportAttributes</a>
</dt>
<dt>
<a href="netvista.allocating_and_freeing_scatter_gather_lists">Allocating and Freeing Scatter/Gather Lists</a>
</dt>
<dt>
<a href="netvista.scatter_gather_dma2">Miniport Driver Scatter/Gather DMA</a>
</dt>
<dt>
<a href="netvista.ndis_scatter_gather_dma">NDIS Scatter/Gather DMA</a>
</dt>
<dt>
<a href="netvista.registering_and_deregistering_dma_channels">Registering and Deregistering DMA Channels</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisMRegisterScatterGatherDma function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

