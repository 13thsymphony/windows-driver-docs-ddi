---
UID: NC:ndis.FREE_SHARED_MEMORY_HANDLER
title: FREE_SHARED_MEMORY_HANDLER
author: windows-driver-content
description: The NetFreeSharedMemory function (FREE_SHARED_MEMORY_HANDLER entry point) is called by NDIS when a driver frees shared memory from a shared memory provider.
old-location: netvista\netfreesharedmemory.htm
old-project: netvista
ms.assetid: fdc3dfe7-6980-493d-ad41-aed501db3a6b
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FREE_SHARED_MEMORY_HANDLER, NetFreeSharedMemory, NetFreeSharedMemory callback function [Network Drivers Starting with Windows Vista], ndis/NetFreeSharedMemory, ndis_shared_memory_ref_15b5aca1-e5be-4063-812f-9d98a4e72cd4.xml, netvista.netfreesharedmemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	NetFreeSharedMemory
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---


# FREE_SHARED_MEMORY_HANDLER callback function
The 
  <i>NetFreeSharedMemory</i> function (FREE_SHARED_MEMORY_HANDLER entry point) is called by NDIS when a driver
  frees shared memory from a shared memory provider.

## Syntax

```
FREE_SHARED_MEMORY_HANDLER FreeSharedMemoryHandler;

void FreeSharedMemoryHandler(
  NDIS_HANDLE ProviderContext,
  NDIS_HANDLE SharedMemoryProviderContext
)
{...}
```

## Parameters

`ProviderContext`

An NDIS_HANDLE to a block of driver-allocated context information that identifies the provider.
     The provider supplied this information in the 
     <b>ProviderContext</b> member of the 
     <a href="..\ndis\ns-ndis-_ndis_shared_memory_provider_characteristics.md">
     NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</a> structure.

`SharedMemoryProviderContext`

A handle for a context area that identifies the shared memory block. This is the handle that the
     shared memory provider supplied at the 
     <i>pSharedMemoryProviderContext</i> parameter of the 
     <a href="..\ndis\nc-ndis-allocate_shared_memory_handler.md">
     NetAllocateSharedMemory</a> function.


## Return Value

None

## Remarks

NDIS calls the 
    <i>NetFreeSharedMemory</i> function of a shared memory provider when a driver calls the 
    <a href="..\ndis\nf-ndis-ndisfreesharedmemory.md">NdisFreeSharedMemory</a> function.

The shared memory provider specified the entry point (FREE_SHARED_MEMORY_HANDLER) for 
    <i>NetFreeSharedMemory</i> in the 
    <a href="..\ndis\ns-ndis-_ndis_shared_memory_provider_characteristics.md">
    NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.20 and later.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ndis\nf-ndis-ndisfreesharedmemory.md">NdisFreeSharedMemory</a>



<a href="..\ndis\nc-ndis-allocate_shared_memory_handler.md">NetAllocateSharedMemory</a>



<a href="..\ndis\ns-ndis-_ndis_shared_memory_provider_characteristics.md">
   NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FREE_SHARED_MEMORY_HANDLER callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>