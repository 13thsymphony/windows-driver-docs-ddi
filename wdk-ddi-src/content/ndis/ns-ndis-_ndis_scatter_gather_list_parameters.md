---
UID: NS.NDIS._NDIS_SCATTER_GATHER_LIST_PARAMETERS
title: _NDIS_SCATTER_GATHER_LIST_PARAMETERS
author: windows-driver-content
description: The NDIS_SCATTER_GATHER_LIST_PARAMETERS structure specifies parameters that NDIS uses to build a scatter/gather list for a buffer.
old-location: netvista\ndis_scatter_gather_list_parameters.htm
old-project: NetVista
ms.assetid: 5c14a6ed-3180-41d6-a09a-b3ae0a0c8b36
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDIS_SCATTER_GATHER_LIST_PARAMETERS, NDIS_SCATTER_GATHER_LIST_PARAMETERS, PNDIS_SCATTER_GATHER_LIST_PARAMETERS, *PNDIS_SCATTER_GATHER_LIST_PARAMETERS
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
req.alt-api: NDIS_SCATTER_GATHER_LIST_PARAMETERS
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
req.irql: See Remarks section
---

# _NDIS_SCATTER_GATHER_LIST_PARAMETERS structure



## -description
The NDIS_SCATTER_GATHER_LIST_PARAMETERS structure specifies parameters that NDIS uses to build a
  scatter/gather list for a buffer.



## -syntax

````
typedef struct _NDIS_SCATTER_GATHER_LIST_PARAMETERS {
  NDIS_OBJECT_HEADER           Header;
  ULONG                        Flags;
  NDIS_RECEIVE_QUEUE_ID        QueueId;
  NDIS_SHARED_MEMORY_USAGE     SharedMemoryUsage;
  PMDL                         Mdl;
  PVOID                        CurrentVa;
  ULONG                        Length;
  NDIS_PROCESS_SG_LIST_HANDLER ProcessSGListHandler;
  PVOID                        Context;
  PSCATTER_GATHER_LIST         ScatterGatherListBuffer;
  ULONG                        ScatterGatherListBufferSize;
  ULONG                        ScatterGatherListBufferSizeNeeded;
} NDIS_SCATTER_GATHER_LIST_PARAMETERS, *PNDIS_SCATTER_GATHER_LIST_PARAMETERS;
````


## -struct-fields

### -field Header

The 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     structure (NDIS_SCATTER_GATHER_LIST_PARAMETERS). The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_SCATTER_GATHER_LIST_PARAMETERS_REVISION_1 and the 
     <b>Size</b> member to NDIS_SIZEOF_SCATTER_GATHER_LIST_PARAMETERS_REVISION_1.


### -field Flags

Reserved for NDIS.


### -field QueueId

An NDIS_RECEIVE_QUEUE_ID type value that contains a queue identifier. The queue identifier is an
     integer between zero and the number of queues that the miniport adapter supports. A zero value indicates
     the default queue.


### -field SharedMemoryUsage

An 
     <a href="netvista.ndis_shared_memory_usage">NDIS_SHARED_MEMORY_USAGE</a> enumeration
     value that specifies the purpose of the shared memory.


### -field Mdl

A pointer to a memory descriptor list (MDL) that describes the shared memory buffer.


### -field CurrentVa

A ULONG value for the current virtual address.


### -field Length

A ULONG value that contains the length, in bytes, of the shared memory buffer.


### -field ProcessSGListHandler

A pointer to a 
     <a href="..\ndis\nc-ndis-ndis_process_sg_list.md">NetProcessSGList</a> function
     (NDIS_PROCESS_SG_LIST_HANDLER entry point).


### -field Context

A pointer to a block of driver-allocated context information that stores information about the
     scatter/gather list. NDIS passes the context information in calls to 
     <a href="..\ndis\nc-ndis-ndis_process_sg_list.md">NetProcessSGList</a> at the 
     <i>Context</i> parameter.


### -field ScatterGatherListBuffer

A pointer to a 
     <a href="kernel.scatter_gather_list">SCATTER_GATHER_LIST</a> structure.


### -field ScatterGatherListBufferSize

A ULONG value that contains the length, in bytes, of the scatter/gather list.


### -field ScatterGatherListBufferSizeNeeded

A ULONG value where NDIS writes the total number of bytes that NDIS requires to build the
     scatter/gather list successfully.


## -remarks
To build a scatter/gather list, an NDIS driver passes the NDIS_SCATTER_GATHER_LIST_PARAMETERS
    structure to the 
    <a href="netvista.ndisbuildscattergatherlist">
    NdisBuildScatterGatherList</a> function.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.20 and later.

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
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndis_shared_memory_usage">NDIS_SHARED_MEMORY_USAGE</a>
</dt>
<dt>
<a href="netvista.ndisbuildscattergatherlist">NdisBuildScatterGatherList</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-ndis_process_sg_list.md">NetProcessSGList</a>
</dt>
<dt>
<a href="kernel.scatter_gather_list">SCATTER_GATHER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDIS_SCATTER_GATHER_LIST_PARAMETERS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

