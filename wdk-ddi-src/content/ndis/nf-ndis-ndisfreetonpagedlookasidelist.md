---
UID: NF:ndis.NdisFreeToNPagedLookasideList
title: NdisFreeToNPagedLookasideList macro
author: windows-driver-content
description: The NdisFreeToNPagedLookasideList function returns an entry to the given lookaside list.
old-location: netvista\ndisfreetonpagedlookasidelist.htm
old-project: netvista
ms.assetid: 2405a405-177a-420a-9628-a340e0d0acb3
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisFreeToNPagedLookasideList, NdisFreeToNPagedLookasideList macro [Network Drivers Starting with Windows Vista], ndis/NdisFreeToNPagedLookasideList, ndis_lookaside_ref_8c12e884-8f7b-4bcc-9631-2173003e4ef6.xml, netvista.ndisfreetonpagedlookasidelist
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisFreeToNPagedLookasideList (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisFreeToNPagedLookasideList (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisFreeToNPagedLookasideList
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisFreeToNPagedLookasideList function
The 
  <b>NdisFreeToNPagedLookasideList</b> function returns an entry to the given lookaside list.

## Syntax

```
void NdisFreeToNPagedLookasideList(
   _L,
   _E
);
```

## Parameters

`_L`

TBD

`_E`

TBD


## Return Value

None

## Remarks

If the lookaside list has not reached the system-determined maximum number of entries, 
    <i>Entry</i> is inserted at the front of the lookaside list. If the list has reached its maximum size, 
    <i>Entry</i> is released to nonpaged pool. That is, 
    <b>NdisFreeToNPagedLookasideList</b> either calls the driver's 
    <i>Free</i> function, specified in the 
    <i>Free</i> parameter if the driver provided one to the 
    <a href="https://msdn.microsoft.com/d240f2cc-18a6-4c2d-889f-e25a9486d5fe">
    NdisInitializeNPagedLookasideList</a> function, or it frees the given entry itself.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisFreeToNPagedLookasideList (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisFreeToNPagedLookasideList (NDIS 5.1)) in Windows XP.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_Miscellaneous_Function |

## See Also

<a href="https://msdn.microsoft.com/df690a05-359d-44f0-b063-4fc21d6c4d76">
   NdisAllocateFromNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/0622d3db-8d28-4c15-a3d8-1092487b8096">
   NdisDeleteNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/d240f2cc-18a6-4c2d-889f-e25a9486d5fe">
   NdisInitializeNPagedLookasideList</a>