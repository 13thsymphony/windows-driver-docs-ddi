---
UID: NF:ndis.NdisGetPoolFromNetBufferList
title: NdisGetPoolFromNetBufferList function
author: windows-driver-content
description: Call the NdisGetPoolFromNetBufferList function to get the NET_BUFFER_LIST structure pool handle that is associated with a specified NET_BUFFER_LIST structure.
old-location: netvista\ndisgetpoolfromnetbufferlist.htm
old-project: netvista
ms.assetid: 645fd5f6-32b5-4ef6-9583-1418291d55d3
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisGetPoolFromNetBufferList, NdisGetPoolFromNetBufferList function [Network Drivers Starting with Windows Vista], ndis/NdisGetPoolFromNetBufferList, ndis_netbuf_functions_ref_c93c9420-04fb-42f7-9844-29c3b2052b82.xml, netvista.ndisgetpoolfromnetbufferlist
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
-	NdisGetPoolFromNetBufferList
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisGetPoolFromNetBufferList function
Call the 
  <b>NdisGetPoolFromNetBufferList</b> function to get the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure pool handle that is
  associated with a specified NET_BUFFER_LIST structure.

## Syntax

```
NDIS_HANDLE NdisGetPoolFromNetBufferList(
  PNET_BUFFER_LIST NetBufferList
);
```

## Parameters

`NetBufferList`

A pointer to a previously allocated 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.


## Return Value

<b>NdisGetPoolFromNetBufferList</b> returns a handle to the NET_BUFFER_LIST structure pool that is
     associated with the specified NET_BUFFER_LIST structure.

## Remarks

The handle that 
    <b>NdisGetPoolFromNetBufferList</b> returns is a required parameter in calls to NDIS functions that
    manipulate the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures that are from the
    associated NET_BUFFER_LIST structure pool.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>