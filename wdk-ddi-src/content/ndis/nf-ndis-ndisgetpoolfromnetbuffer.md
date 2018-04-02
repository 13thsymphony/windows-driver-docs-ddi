---
UID: NF:ndis.NdisGetPoolFromNetBuffer
title: NdisGetPoolFromNetBuffer function
author: windows-driver-content
description: Call the NdisGetPoolFromNetBuffer function to get the NET_BUFFER structure pool handle that is associated with a specified NET_BUFFER structure.
old-location: netvista\ndisgetpoolfromnetbuffer.htm
old-project: netvista
ms.assetid: 64bb049a-6b8a-470f-8269-8a168761e388
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisGetPoolFromNetBuffer, NdisGetPoolFromNetBuffer function [Network Drivers Starting with Windows Vista], ndis/NdisGetPoolFromNetBuffer, ndis_netbuf_functions_ref_ae9f36c7-ab1c-4ea4-9721-2fd15aabc667.xml, netvista.ndisgetpoolfromnetbuffer
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
-	NdisGetPoolFromNetBuffer
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisGetPoolFromNetBuffer function
Call the 
  <b>NdisGetPoolFromNetBuffer</b> function to get the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure pool handle that is associated
  with a specified NET_BUFFER structure.

## Syntax

```
NDIS_HANDLE NdisGetPoolFromNetBuffer(
  PNET_BUFFER NetBuffer
);
```

## Parameters

`NetBuffer`

A pointer to a previously allocated 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure.


## Return Value

<b>NdisGetPoolFromNetBuffer</b> returns a handle to the NET_BUFFER structure pool that is associated with
     the specified NET_BUFFER structure.

## Remarks

The handle that 
    <b>NdisGetPoolFromNetBuffer</b> returns is a required parameter in calls to NDIS functions that manipulate
    
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures that are from the
    associated NET_BUFFER structure pool.

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