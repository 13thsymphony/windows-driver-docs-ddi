---
UID: NF:ndis.NdisFreeMemoryWithTag
title: NdisFreeMemoryWithTag function
author: windows-driver-content
description: The NdisFreeMemoryWithTag function is deprecated for all NDIS versions. Use NdisAllocateMemoryWithTagPriority instead.
old-location: netvista\ndisfreememorywithtag.htm
old-project: netvista
ms.assetid: c9010a08-3c62-481a-8545-253d7b24b1ac
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ndis_shared_memory_ref_2a68decc-2cef-4606-9679-c29c0e5362a2.xml, NdisFreeMemoryWithTag function [Network Drivers Starting with Windows Vista], netvista.ndisfreememorywithtag, NdisFreeMemoryWithTag, ndis/NdisFreeMemoryWithTag
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
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisFreeMemoryWithTag
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisFreeMemoryWithTag function
The 
  <b>NdisFreeMemoryWithTag</b> function is deprecated for all NDIS versions.  Use <a href="..\ndis\nf-ndis-ndisallocatememorywithtagpriority.md">NdisAllocateMemoryWithTagPriority</a> instead.

## Syntax

````
VOID NdisFreeMemoryWithTag(
  _In_ PVOID VirtualAddress,
  _In_ ULONG Tag
);
````

## Parameters

`VirtualAddress`

A pointer to the base virtual address of the allocated memory. This address was returned by the 
     <a href="https://msdn.microsoft.com/0dae26f7-0c00-4a5c-a447-825290ab6570">
     NdisAllocateMemoryWithTag</a> function.

`Tag`

A string, delimited by single quotation marks, with up to four characters, usually specified in
     reversed order. The NDIS-supplied default tag for this call is 'maDN', but the caller can override this
     default by supplying an explicit value.


## Return Value

None

## Remarks

Because noncached memory and contiguous memory are seldom released until the allocating miniport
    driver is unloading, a caller of 
    <b>NdisFreeMemoryWithTag</b> usually is running at IRQL = PASSIVE_LEVEL for these types of de-allocations.
    In any case:

<ul>
<li>
When a caller of 
      <b>NdisFreeMemoryWithTag</b> releases contiguous memory, it must be running at IRQL = PASSIVE_LEVEL.

</li>
<li>
When a caller of 
      <b>NdisFreeMemoryWithTag</b> releases noncached memory, it must be running at IRQL &lt;
      DISPATCH_LEVEL.

</li>
<li>
When a caller of 
      <b>NdisFreeMemoryWithTag</b> releases memory that is neither contiguous nor noncached, it must be
      running at IRQL &lt;= DISPATCH_LEVEL.

</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.20 and later.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | See Remarks section. |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550767">NdisAllocateMemoryWithTag</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFreeMemoryWithTag function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>