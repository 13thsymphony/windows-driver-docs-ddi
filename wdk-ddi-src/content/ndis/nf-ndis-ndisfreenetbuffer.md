---
UID: NF:ndis.NdisFreeNetBuffer
title: NdisFreeNetBuffer function
author: windows-driver-content
description: Call the NdisFreeNetBuffer function to free a NET_BUFFER structure that was previously allocated from a NET_BUFFER structure pool with the NdisAllocateNetBuffer function.
old-location: netvista\ndisfreenetbuffer.htm
old-project: netvista
ms.assetid: 9b5fe91b-29ae-4c83-b405-4a90e4375b4a
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisFreeNetBuffer, NdisFreeNetBuffer function [Network Drivers Starting with Windows Vista], ndis/NdisFreeNetBuffer, ndis_netbuf_functions_ref_623498b1-25e0-48ae-831e-8c1240106bd4.xml, netvista.ndisfreenetbuffer
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
req.ddi-compliance: Irql_NetBuffer_Function, NdisAllocateNetBuffer
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
-	NdisFreeNetBuffer
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisFreeNetBuffer function
Call the 
  <b>NdisFreeNetBuffer</b> function to free a 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure that was previously allocated
  from a NET_BUFFER structure pool with the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff561607">NdisAllocateNetBuffer</a> function.

## Syntax

```
void NdisFreeNetBuffer(
  __drv_freesMem(mem)PNET_BUFFER NetBuffer
);
```

## Parameters

`NetBuffer`

A pointer to a NET_BUFFER structure that was allocated by calling 
     <b>NdisAllocateNetBuffer</b>.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_NetBuffer_Function, NdisAllocateNetBuffer |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561607">NdisAllocateNetBuffer</a>