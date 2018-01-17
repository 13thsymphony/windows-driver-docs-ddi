---
UID: NF:ndis.NdisAllocateSharedMemory
title: NdisAllocateSharedMemory function
author: windows-driver-content
description: The NdisAllocateSharedMemory function allocates shared memory from a shared memory provider.
old-location: netvista\ndisallocatesharedmemory.htm
old-project: netvista
ms.assetid: 1e4919df-7897-44c3-876f-0f1acfe6d5af
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisAllocateSharedMemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisAllocateSharedMemory
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE
---

# NdisAllocateSharedMemory function



## -description
The 
  <b>NdisAllocateSharedMemory</b> function allocates shared memory from a shared memory provider.



## -syntax

````
NDIS_STATUS NdisAllocateSharedMemory(
  _In_    NDIS_HANDLE                    NdisHandle,
  _In_    PNDIS_SHARED_MEMORY_PARAMETERS SharedMemoryParameters,
  _Inout_ PNDIS_HANDLE                   pAllocationHandle
);
````


## -parameters

### -param NdisHandle [in]

An NDIS driver or instance handle that was obtained during caller initialization. For example, a
     miniport driver can use the NDIS handle that it obtained from the 
     <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
     NdisMRegisterMiniportDriver</a> or 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function.
     Other NDIS drivers can use the handles from the following functions:
     

<dl>
<dd>

<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a>


</dd>
<dd>

<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>


</dd>
</dl>

### -param SharedMemoryParameters [in]

A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_shared_memory_parameters.md">
     NDIS_SHARED_MEMORY_PARAMETERS</a> structure that defines the requested attributes for the shared
     memory.


### -param pAllocationHandle [in, out]

A pointer to a location for a handle that identifies the shared memory that was allocated. The
     handle is available when the function returns or it is <b>NULL</b> if the function fails. The caller must use
     this handle to free the shared memory that was allocated successfully.


## -returns
<b>NdisAllocateSharedMemory</b> can return the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>The operation failed because there were insufficient resources to complete the operation.
<dl>
<dt><b>NDIS_STATUS_INVALID_PARAMETER</b></dt>
</dl>The operation failed because of an invalid input parameter.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>The operation failed for unspecified reasons.

 


## -remarks
NDIS drivers call the 
    <b>NdisAllocateSharedMemory</b> function to allocate a block of shared memory from an NDIS shared memory
    provider.

The 
    <i>SharedMemoryParameters</i> parameter contains a pointer to an 
    <a href="..\ndis\ns-ndis-_ndis_shared_memory_parameters.md">
    NDIS_SHARED_MEMORY_PARAMETERS</a> structure that defines the requested attributes for the shared
    memory. If the <b>NDIS_SHARED_MEM_PARAMETERS_CONTIGUOUS</b> flag is not set in the 
    <b>Flags</b> member, shared memory can be specified in a scatter-gather list that is contained in
    non-contiguous memory.

NDIS calls the 
    <a href="..\ndis\nc-ndis-allocate_shared_memory_handler.md">NetAllocateSharedMemory</a> function of a shared memory provider from the context of the call to 
    <b>NdisAllocateSharedMemory</b>.

The driver must call the 
    <a href="..\ndis\nf-ndis-ndisfreesharedmemory.md">NdisFreeSharedMemory</a> function to free
    the shared memory that it allocates with 
    <b>NdisAllocateSharedMemory</b>.


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_shared_memory_parameters.md">NDIS_SHARED_MEMORY_PARAMETERS</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">NdisFRegisterFilterDriver</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfreesharedmemory.md">NdisFreeSharedMemory</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterdmachannel.md">NdisMRegisterDmaChannel</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterscattergatherdma.md">
   NdisMRegisterScatterGatherDma</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-allocate_shared_memory_handler.md">NetAllocateSharedMemory</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAllocateSharedMemory function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

