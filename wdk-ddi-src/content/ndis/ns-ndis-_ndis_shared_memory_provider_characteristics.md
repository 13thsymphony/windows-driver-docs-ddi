---
UID: NS:ndis._NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS
title: "_NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS"
author: windows-driver-content
description: The NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure specifies shared memory provider characteristics.
old-location: netvista\ndis_shared_memory_provider_characteristics.htm
old-project: netvista
ms.assetid: 45001da1-5fe3-4383-8da7-31e3ee115c1f
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, PNDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, ndis/NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, ndis/PNDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, ndis_shared_memory_ref_0cb54ab1-d469-4fa0-833a-eb17e1441e76.xml, netvista.ndis_shared_memory_provider_characteristics"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, *PNDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS
---

# _NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure
The NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure specifies shared memory provider
  characteristics.

## Syntax
````
typedef struct _NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS {
  NDIS_OBJECT_HEADER             Header;
  ULONG                          Flags;
  NDIS_HANDLE                    ProviderContext;
  ALLOCATE_SHARED_MEMORY_HANDLER AllocateSharedMemoryHandler;
  FREE_SHARED_MEMORY_HANDLER     FreeSharedMemoryHandler;
} NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, *PNDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS;
````

## Members


`Header`

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     structure (NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS). The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_SHARED_MEMORY_PROVIDER_CHARACTERISTICS, the 
     <b>Revision</b> member to NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_SHARED_MEMORY_PROVIDER_CHARACTERISTICS_REVISION_1.

`Flags`

Reserved for NDIS.

`ProviderContext`

An NDIS_HANDLE to a block of driver-allocated context information that stores information about
     the provider. NDIS passes the context information in calls to 
     <i>NetXxxSharedMemory</i> functions at the 
     <i>ProviderContext</i> parameter.

`AllocateSharedMemoryHandler`

An entry point for the 
     <a href="..\ndis\nc-ndis-allocate_shared_memory_handler.md">
     NetAllocateSharedMemory</a> function.

`FreeSharedMemoryHandler`

An entry point for the 
     <a href="..\ndis\nc-ndis-free_shared_memory_handler.md">NetFreeSharedMemory</a> function.

## Remarks
To specify entry points for shared memory services, an NDIS driver initializes an
    NDIS_SHARED_MEMORY_PROVIDER_CHARACTERISTICS structure and passes it to the 
    <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">
    NdisSetOptionalHandlers</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.20 and later. Supported in NDIS 6.20 and later. |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<a href="..\ndis\nc-ndis-free_shared_memory_handler.md">NetFreeSharedMemory</a>



<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>



<a href="..\ndis\nc-ndis-allocate_shared_memory_handler.md">NetAllocateSharedMemory</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>