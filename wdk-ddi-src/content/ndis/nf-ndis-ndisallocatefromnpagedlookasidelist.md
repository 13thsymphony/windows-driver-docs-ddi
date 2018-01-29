---
UID : NF:ndis.NdisAllocateFromNPagedLookasideList
title : NdisAllocateFromNPagedLookasideList macro
author : windows-driver-content
description : The NdisAllocateFromNPagedLookasideList function removes the first entry from the given lookaside list head. If the lookaside list currently is empty, an entry is allocated from nonpaged pool.
old-location : netvista\ndisallocatefromnpagedlookasidelist.htm
old-project : netvista
ms.assetid : df690a05-359d-44f0-b063-4fc21d6c4d76
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ndis/NdisAllocateFromNPagedLookasideList, ndis_lookaside_ref_455986e8-a34c-44df-b454-87416d8eccf7.xml, NdisAllocateFromNPagedLookasideList macro [Network Drivers Starting with Windows Vista], NdisAllocateFromNPagedLookasideList, netvista.ndisallocatefromnpagedlookasidelist
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Desktop
req.target-min-winverclnt : Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisAllocateFromNPagedLookasideList (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers   (see       NdisAllocateFromNPagedLookasideList (NDIS 5.1)) in Windows XP.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : Irql_Miscellaneous_Function
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : ndis.h
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisAllocateFromNPagedLookasideList function
The 
  <b>NdisAllocateFromNPagedLookasideList</b> function removes the first entry from the given lookaside list
  head. If the lookaside list currently is empty, an entry is allocated from nonpaged pool.

## Syntax

````
PVOID NdisAllocateFromNPagedLookasideList(
  [in] PNPAGED_LOOKASIDE_LIST Lookaside
);
````

## Parameters

`_L`

TBD


## Return Value

None

## Remarks

If the lookaside list is not empty, 
    <b>NdisAllocateFromNPagedLookasideList</b> removes the first entry from the list and returns its address
    to the caller. If the lookaside list is empty, 
    <b>NdisAllocateFromNPagedLookasideList</b> either calls the 
    <i>Allocate</i> function, specified in the 
    <i>Allocate</i> parameter of the 
    <mshelp:link keywords="netvista.ndisinitializenpagedlookasidelist" tabindex="0"><b>
    NdisInitializeNPagedLookasideList</b></mshelp:link> function, that the caller specified at list initialization, if
    any, or it allocates an entry on behalf of the caller. 
    <b>NdisAllocateFromNPagedLookasideList</b> returns <b>NULL</b> if the caller-supplied 
    <i>Allocate</i> function, if any, or if this function itself cannot allocate an nonpaged entry.

All entries that are allocated from a nonpaged lookaside list are of a fixed size, that was specified
    when the driver originally called 
    <b>NdisInitializeNPagedLookasideList</b>. Consequently, a lookaside list is particularly useful to
    drivers that must allocate fixed-size blocks in which to maintain state in response to dynamic I/O
    demand. For example, any connection-oriented NDIS driver might allocate the VC context areas that it
    needs from a lookaside list as VCs are created and release each such entry back to the lookaside list
    with the 
    <mshelp:link keywords="netvista.ndisfreetonpagedlookasidelist" tabindex="0"><b>
    NdisFreeToNPagedLookasideList</b></mshelp:link> function as each VC is torn down.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** | Irql_Miscellaneous_Function |

## See Also

<mshelp:link keywords="netvista.ndisdeletenpagedlookasidelist" tabindex="0"><b>
   NdisDeleteNPagedLookasideList</b></mshelp:link>

<mshelp:link keywords="netvista.ndisfreetonpagedlookasidelist" tabindex="0"><b>
   NdisFreeToNPagedLookasideList</b></mshelp:link>

<mshelp:link keywords="netvista.ndisinitializenpagedlookasidelist" tabindex="0"><b>
   NdisInitializeNPagedLookasideList</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAllocateFromNPagedLookasideList macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>