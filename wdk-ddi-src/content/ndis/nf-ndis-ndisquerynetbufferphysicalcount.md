---
UID: NF:ndis.NdisQueryNetBufferPhysicalCount
title: NdisQueryNetBufferPhysicalCount function
author: windows-driver-content
description: The NdisQueryNetBufferPhysicalCount function returns the maximum number of physical breaks mapped by the buffer descriptors that are associated with the given NET_BUFFER structure.
old-location: netvista\ndisquerynetbufferphysicalcount.htm
old-project: netvista
ms.assetid: 99869b20-3458-426a-ad64-c2cc54213290
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisQueryNetBufferPhysicalCount, NdisQueryNetBufferPhysicalCount function [Network Drivers Starting with Windows Vista], ndis/NdisQueryNetBufferPhysicalCount, ndis_netbuf_functions_ref_d041f487-3273-402e-8726-d9a252b1dd45.xml, netvista.ndisquerynetbufferphysicalcount
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
-	NdisQueryNetBufferPhysicalCount
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisQueryNetBufferPhysicalCount function
The 
  <b>NdisQueryNetBufferPhysicalCount</b> function returns the maximum number of physical breaks mapped by the
  buffer descriptors that are associated with the given 
  <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure.

## Syntax

````
ULONG NdisQueryNetBufferPhysicalCount(
  _In_ PNET_BUFFER NetBuffer
);
````

## Parameters

`NetBuffer`

A pointer to a previously allocated 
     <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure.


## Return Value

<b>NdisQueryNetBufferPhysicalCount</b> returns a ULONG value containing a count of the maximum number of
     physical breaks, mapped by MDLs that are associated with the specified NET_BUFFER structure.


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

<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>