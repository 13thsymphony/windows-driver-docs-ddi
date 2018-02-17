---
UID: NF:ndis.NdisQueryDepthSList
title: NdisQueryDepthSList macro
author: windows-driver-content
description: The NdisQueryDepthSList function returns the current number of entries in a given sequenced, singly linked list.
old-location: netvista\ndisquerydepthslist.htm
old-project: netvista
ms.assetid: 76b076d1-640b-4378-bf6d-36d87a8a5042
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisQueryDepthSList macro [Network Drivers Starting with Windows Vista], NdisQueryDepthSList, netvista.ndisquerydepthslist, ndis/NdisQueryDepthSList, ndis_interlocked_ref_f44c64cf-029a-408e-84a0-a8c09bc91592.xml
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
-	NdisQueryDepthSList
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
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
| **Library** | ndis.h |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_Miscellaneous_Function |

## See Also

<a href="..\ndis\nf-ndis-ndisinterlockedpopentryslist.md">NdisInterlockedPopEntrySList</a>



<a href="..\ndis\nf-ndis-ndisinitializeslisthead.md">NdisInitializeSListHead</a>



<a href="..\ndis\nf-ndis-ndisinterlockedpushentryslist.md">
   NdisInterlockedPushEntrySList</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisQueryDepthSList macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>