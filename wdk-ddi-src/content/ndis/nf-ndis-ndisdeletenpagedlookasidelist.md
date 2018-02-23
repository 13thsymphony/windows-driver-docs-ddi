---
UID: NF:ndis.NdisDeleteNPagedLookasideList
title: NdisDeleteNPagedLookasideList macro
author: windows-driver-content
description: The NdisDeleteNPagedLookasideList function removes a nonpaged lookaside list from the system.
old-location: netvista\ndisdeletenpagedlookasidelist.htm
old-project: netvista
ms.assetid: 0622d3db-8d28-4c15-a3d8-1092487b8096
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ndis/NdisDeleteNPagedLookasideList, NdisDeleteNPagedLookasideList, ndis_lookaside_ref_37df3d7d-0aa7-4d8e-b6a5-38ab85ca929e.xml, netvista.ndisdeletenpagedlookasidelist, NdisDeleteNPagedLookasideList macro [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisDeleteNPagedLookasideList (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisDeleteNPagedLookasideList (NDIS 5.1)) in Windows XP.
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
req.lib: ndis.h
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NdisDeleteNPagedLookasideList
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisDeleteNPagedLookasideList function
The 
  <b>NdisDeleteNPagedLookasideList</b> function removes a nonpaged lookaside list from the system.

## Syntax

````
VOID NdisDeleteNPagedLookasideList(
  [in] PNPAGED_LOOKASIDE_LIST Lookaside
);
````

## Parameters

`_L`

TBD


## Return Value

None

## Remarks

After freeing any remaining entries in the given lookaside list, 
    <b>NdisDeleteNPagedLookasideList</b> removes the list from the OS-maintained set of nonpaged lookaside
    lists.

However, 
    <b>NdisDeleteNPagedLookasideList</b> does not free the list head, for which the caller originally
    allocated the memory. An NDIS driver is responsible for calling the 
    <a href="..\ndis\nf-ndis-ndisfreememory.md">NdisFreeMemory</a> function to release any
    memory that it allocated.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisDeleteNPagedLookasideList (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisDeleteNPagedLookasideList (NDIS 5.1)) in Windows XP.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | ndis.h |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_Miscellaneous_Function |

## See Also

<a href="..\ndis\nf-ndis-ndisallocatefromnpagedlookasidelist.md">
   NdisAllocateFromNPagedLookasideList</a>



<a href="..\ndis\nf-ndis-ndisfreetonpagedlookasidelist.md">
   NdisFreeToNPagedLookasideList</a>



<a href="..\ndis\nf-ndis-ndisinitializenpagedlookasidelist.md">
   NdisInitializeNPagedLookasideList</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisDeleteNPagedLookasideList macro%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>