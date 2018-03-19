---
UID: NF:ndis.NdisFreeScatterGatherList
title: NdisFreeScatterGatherList function
author: windows-driver-content
description: The NdisFreeScatterGatherList function frees a scatter/gather list.
old-location: netvista\ndisfreescattergatherlist.htm
old-project: netvista
ms.assetid: 140be989-e578-4bfe-8b9e-56abb274933a
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisFreeScatterGatherList, NdisFreeScatterGatherList function [Network Drivers Starting with Windows Vista], ndis/NdisFreeScatterGatherList, ndis_shared_memory_ref_2376e740-d44c-4572-8731-7518d4765208.xml, netvista.ndisfreescattergatherlist
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
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
req.lib: Ndis.lib
req.dll: 
req.irql: "= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisFreeScatterGatherList
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisFreeScatterGatherList function
The 
  <b>NdisFreeScatterGatherList</b> function frees a scatter/gather list.

## Syntax

````
VOID NdisFreeScatterGatherList(
  _In_ NDIS_HANDLE          NdisHandle,
  _In_ PSCATTER_GATHER_LIST ScatterGatherListBuffer,
  _In_ BOOLEAN              WriteToDevice
);
````

## Parameters

`NdisHandle`

An NDIS driver or instance handle that was obtained during caller initialization. This should be
     the same handle that was passed to the 
     <a href="..\ndis\nf-ndis-ndisbuildscattergatherlist.md">
     NdisBuildScatterGatherList</a> function when the scatter/gather list was created.

`ScatterGatherListBuffer`

A pointer to a caller-provided 
     <a href="..\wdm\ns-wdm-_scatter_gather_list.md">SCATTER_GATHER_LIST</a> structure to free.
     This must be the same buffer that was passed to the 
     <b>NdisBuildScatterGatherList</b> function when the scatter/gather list was allocated.

`WriteToDevice`

A BOOLEAN value that is set to <b>TRUE</b> if the scatter/gather list was used for writing to the device.
     Otherwise, it is <b>FALSE</b>.


## Return Value

None

## Remarks

NDIS drivers call the 
    <b>NdisFreeScatterGatherList</b> function to free a scatter/gather list that was created with the 
    <a href="..\ndis\nf-ndis-ndisbuildscattergatherlist.md">
    NdisBuildScatterGatherList</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.20 and later.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "= DISPATCH_LEVEL" |

## See Also

<a href="..\wdm\ns-wdm-_scatter_gather_list.md">SCATTER_GATHER_LIST</a>



<a href="..\ndis\nf-ndis-ndisbuildscattergatherlist.md">NdisBuildScatterGatherList</a>