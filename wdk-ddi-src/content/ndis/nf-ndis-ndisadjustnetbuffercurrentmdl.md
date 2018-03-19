---
UID: NF:ndis.NdisAdjustNetBufferCurrentMdl
title: NdisAdjustNetBufferCurrentMdl function
author: windows-driver-content
description: The NdisAdjustNetBufferCurrentMdl function updates a NET_BUFFER structure based on the current data offset.
old-location: netvista\ndisadjustnetbuffercurrentmdl.htm
old-project: netvista
ms.assetid: 5d05793b-cb35-435d-aa59-6ac380668d91
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisAdjustNetBufferCurrentMdl, NdisAdjustNetBufferCurrentMdl function [Network Drivers Starting with Windows Vista], ndis/NdisAdjustNetBufferCurrentMdl, ndis_netbuf_functions_ref_a555c8dc-ed71-46b9-8922-32bfad03f2a1.xml, netvista.ndisadjustnetbuffercurrentmdl
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisAdjustNetBufferCurrentMdl
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisAdjustNetBufferCurrentMdl function
The 
  <b>NdisAdjustNetBufferCurrentMdl</b> function updates a 
  <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure based on the current data
  offset.

## Syntax

````
VOID NdisAdjustNetBufferCurrentMdl(
  _In_ PNET_BUFFER NetBuffer
);
````

## Parameters

`NetBuffer`

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure.


## Return Value

None

## Remarks

The 
    <b>NdisAdjustNetBufferCurrentMdl</b> function recalculates and sets the 
    <b>CurrentMdl</b> and 
    <b>CurrentMdlOffset</b> members of a 
    <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure based on the 
    <b>DataOffset</b> member of the NET_BUFFER structure.

Callers of 
    <b>NdisAdjustNetBufferCurrentMdl</b> can run at any IRQL, but typically run at IRQL &lt;=
    DISPATCH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | Any level (see Remarks section) |

## See Also

<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>