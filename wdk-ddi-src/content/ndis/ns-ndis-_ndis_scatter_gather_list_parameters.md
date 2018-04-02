---
UID: NS:ndis._NDIS_SCATTER_GATHER_LIST_PARAMETERS
title: "_NDIS_SCATTER_GATHER_LIST_PARAMETERS"
author: windows-driver-content
description: The NDIS_SCATTER_GATHER_LIST_PARAMETERS structure specifies parameters that NDIS uses to build a scatter/gather list for a buffer.
old-location: netvista\ndis_scatter_gather_list_parameters.htm
old-project: netvista
ms.assetid: 5c14a6ed-3180-41d6-a09a-b3ae0a0c8b36
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_SCATTER_GATHER_LIST_PARAMETERS, NDIS_SCATTER_GATHER_LIST_PARAMETERS, NDIS_SCATTER_GATHER_LIST_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_SCATTER_GATHER_LIST_PARAMETERS, PNDIS_SCATTER_GATHER_LIST_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SCATTER_GATHER_LIST_PARAMETERS, ndis/NDIS_SCATTER_GATHER_LIST_PARAMETERS, ndis/PNDIS_SCATTER_GATHER_LIST_PARAMETERS, ndis_shared_memory_ref_b74a7da6-25c0-4ede-8540-d8fd5ee88ca2.xml, netvista.ndis_scatter_gather_list_parameters"
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
-	NDIS_SCATTER_GATHER_LIST_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_SCATTER_GATHER_LIST_PARAMETERS, *PNDIS_SCATTER_GATHER_LIST_PARAMETERS
---

# _NDIS_SCATTER_GATHER_LIST_PARAMETERS structure
The NDIS_SCATTER_GATHER_LIST_PARAMETERS structure specifies parameters that NDIS uses to build a
  scatter/gather list for a buffer.

## Syntax
```
typedef struct _NDIS_SCATTER_GATHER_LIST_PARAMETERS {
  NDIS_OBJECT_HEADER           Header;
  ULONG                        Flags;
  NDIS_RECEIVE_QUEUE_ID        QueueId;
  NDIS_SHARED_MEMORY_USAGE     SharedMemoryUsage;
  PMDL                         Mdl;
  PVOID                        CurrentVa;
  ULONG                        Length;
  NDIS_PROCESS_SG_LIST_HANDLER ProcessSGListHandler;
  PVOID                        Context;
  PSCATTER_GATHER_LIST         ScatterGatherListBuffer;
  ULONG                        ScatterGatherListBufferSize;
  ULONG                        ScatterGatherListBufferSizeNeeded;
} NDIS_SCATTER_GATHER_LIST_PARAMETERS, *PNDIS_SCATTER_GATHER_LIST_PARAMETERS;
```

## Members


`Header`

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     structure (NDIS_SCATTER_GATHER_LIST_PARAMETERS). The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_SCATTER_GATHER_LIST_PARAMETERS_REVISION_1 and the 
     <b>Size</b> member to NDIS_SIZEOF_SCATTER_GATHER_LIST_PARAMETERS_REVISION_1.

`Flags`

Reserved for NDIS.

`QueueId`

An NDIS_RECEIVE_QUEUE_ID type value that contains a queue identifier. The queue identifier is an
     integer between zero and the number of queues that the miniport adapter supports. A zero value indicates
     the default queue.

`SharedMemoryUsage`

An 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff567309">NDIS_SHARED_MEMORY_USAGE</a> enumeration
     value that specifies the purpose of the shared memory.

`Mdl`

A pointer to a memory descriptor list (MDL) that describes the shared memory buffer.

`CurrentVa`

A ULONG value for the current virtual address.

`Length`

A ULONG value that contains the length, in bytes, of the shared memory buffer.

`ProcessSGListHandler`

A pointer to a 
     <a href="https://msdn.microsoft.com/5b99e0ec-7c82-46d6-b32a-246b368cf4f1">NetProcessSGList</a> function
     (NDIS_PROCESS_SG_LIST_HANDLER entry point).

`Context`

A pointer to a block of driver-allocated context information that stores information about the
     scatter/gather list. NDIS passes the context information in calls to 
     <a href="https://msdn.microsoft.com/5b99e0ec-7c82-46d6-b32a-246b368cf4f1">NetProcessSGList</a> at the 
     <i>Context</i> parameter.

`ScatterGatherListBuffer`

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563664">SCATTER_GATHER_LIST</a> structure.

`ScatterGatherListBufferSize`

A ULONG value that contains the length, in bytes, of the scatter/gather list.

`ScatterGatherListBufferSizeNeeded`

A ULONG value where NDIS writes the total number of bytes that NDIS requires to build the
     scatter/gather list successfully.

## Remarks
To build a scatter/gather list, an NDIS driver passes the NDIS_SCATTER_GATHER_LIST_PARAMETERS
    structure to the 
    <a href="https://msdn.microsoft.com/439d68ec-9d27-484b-b6a3-9bae732d142e">
    NdisBuildScatterGatherList</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.20 and later. Supported in NDIS 6.20 and later. |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567309">NDIS_SHARED_MEMORY_USAGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561620">NdisBuildScatterGatherList</a>



<a href="https://msdn.microsoft.com/5b99e0ec-7c82-46d6-b32a-246b368cf4f1">NetProcessSGList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563664">SCATTER_GATHER_LIST</a>