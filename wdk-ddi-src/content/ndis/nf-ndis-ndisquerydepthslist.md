---
UID: NF:ndis.NdisQueryDepthSList
title: NdisQueryDepthSList macro
author: windows-driver-content
description: The NdisQueryDepthSList function returns the current number of entries in a given sequenced, singly linked list.
old-location: netvista\ndisquerydepthslist.htm
old-project: netvista
ms.assetid: 76b076d1-640b-4378-bf6d-36d87a8a5042
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisQueryDepthSList, NdisQueryDepthSList macro [Network Drivers Starting with Windows Vista], ndis/NdisQueryDepthSList, ndis_interlocked_ref_f44c64cf-029a-408e-84a0-a8c09bc91592.xml, netvista.ndisquerydepthslist
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisQueryDepthSList (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisQueryDepthSList (NDIS   5.1)) in Windows XP.
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
-	NdisQueryDepthSList
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisQueryDepthSList function
The 
  <b>NdisQueryDepthSList</b> function returns the current number of entries in a given sequenced, singly
  linked list.

## Syntax

````
USHORT NdisQueryDepthSList(
  [in] PSLIST_HEADER SListHead
);
````

## Parameters

`SListHead`

A pointer to the head of the S-List to be queried, which the caller already initialized with 
     <a href="..\ndis\nf-ndis-ndisinitializeslisthead.md">NdisInitializeSListHead</a>.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisQueryDepthSList (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisQueryDepthSList (NDIS   5.1)) in Windows XP.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_Miscellaneous_Function |

## See Also

<a href="..\ndis\nf-ndis-ndisinterlockedpopentryslist.md">NdisInterlockedPopEntrySList</a>



<a href="..\ndis\nf-ndis-ndisinterlockedpushentryslist.md">
   NdisInterlockedPushEntrySList</a>



<a href="..\ndis\nf-ndis-ndisinitializeslisthead.md">NdisInitializeSListHead</a>