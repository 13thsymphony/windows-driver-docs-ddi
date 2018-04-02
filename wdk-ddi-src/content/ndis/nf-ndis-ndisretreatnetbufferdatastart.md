---
UID: NF:ndis.NdisRetreatNetBufferDataStart
title: NdisRetreatNetBufferDataStart function
author: windows-driver-content
description: Call the NdisRetreatNetBufferDataStart function to access more used data space in the MDL chain of a NET_BUFFER structure.
old-location: netvista\ndisretreatnetbufferdatastart.htm
old-project: netvista
ms.assetid: 4b58a1dc-8a5a-464b-a2a2-deb952febe25
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisRetreatNetBufferDataStart, NdisRetreatNetBufferDataStart function [Network Drivers Starting with Windows Vista], ndis/NdisRetreatNetBufferDataStart, ndis_netbuf_functions_ref_1075cc2e-490a-4b90-93d9-269e226e8dde.xml, netvista.ndisretreatnetbufferdatastart
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
req.ddi-compliance: Irql_NetBuffer_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisRetreatNetBufferDataStart
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisRetreatNetBufferDataStart function
Call the 
  <b>NdisRetreatNetBufferDataStart</b> function to access more 
  <i>used data space</i> in the MDL chain of a 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure.

## Syntax

```
NDIS_STATUS NdisRetreatNetBufferDataStart(
  PNET_BUFFER                     NetBuffer,
  ULONG                           DataOffsetDelta,
  ULONG                           DataBackFill,
  NET_BUFFER_ALLOCATE_MDL_HANDLER AllocateMdlHandler
);
```

## Parameters

`NetBuffer`

A pointer to a previously allocated NET_BUFFER structure.

`DataOffsetDelta`

The amount of 
     <i>used data space</i> to add. NDIS adjusts the 
     <b>DataOffset</b> member of the NET_BUFFER structure accordingly. If there is not enough 
     <i>unused data space</i> to satisfy the request, NDIS allocates additional memory.

`DataBackFill`

If NDIS must allocate memory, this parameter specifies the amount of data space, in addition to
     the value of the 
     <i>DataOffsetDelta</i> parameter, to allocate.

`AllocateMdlHandler`

An optional entry point for an 
     <a href="https://msdn.microsoft.com/14247f48-7ef8-481c-aa1e-e657475812fa">NetAllocateMdl</a> function. If the caller
     specifies an entry point for the 
     <i>NetAllocateMdl</i> function, NDIS calls 
     <i>NetAllocateMdl</i> to allocate an MDL and memory.


## Return Value

<b>NdisRetreatNetBufferDataStart</b> returns one of the following:

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
<b>NdisRetreatNetBufferDataStart</b> successfully allocated 
       <i>used data space</i> either by using the 
       <i>unused data space</i> or by allocating new storage.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisRetreatNetBufferDataStart</b> failed due to insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisRetreatNetBufferDataStart</b> failed for reasons other than insufficient resources.

</td>
</tr>
</table>

## Remarks

<b>NdisRetreatNetBufferDataStart</b> attempts to satisfy the request by reducing the value of the 
    <b>DataOffset</b> member of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure.

If there isn't enough 
    <i>unused data space</i>, this function allocates a new buffer and an MDL to describe the new buffer and
    chains the new MDL to the beginning of the MDL chain. NDIS calls the 
    <a href="https://msdn.microsoft.com/14247f48-7ef8-481c-aa1e-e657475812fa">NetAllocateMdl</a> function specified at 
    <i>AllocateMdl</i> to allocate the MDL and memory. The 
    <i>NetAllocateMdl</i> function can use any allocation method that meets the
    driver's design requirements.

Call the 
    <a href="https://msdn.microsoft.com/49b69282-137d-4bb5-92f5-4d27cedbb6d4">
    NdisAdvanceNetBufferDataStart</a> function to release the 
    <i>used data space</i> that was added with 
    <b>NdisRetreatNetBufferDataStart</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_NetBuffer_Function |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/49b69282-137d-4bb5-92f5-4d27cedbb6d4">
   NdisAdvanceNetBufferDataStart</a>



<a href="https://msdn.microsoft.com/14247f48-7ef8-481c-aa1e-e657475812fa">NetAllocateMdl</a>