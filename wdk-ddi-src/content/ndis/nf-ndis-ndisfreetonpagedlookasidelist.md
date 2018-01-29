---
UID : NF:ndis.NdisFreeToNPagedLookasideList
title : NdisFreeToNPagedLookasideList macro
author : windows-driver-content
description : The NdisFreeToNPagedLookasideList function returns an entry to the given lookaside list.
old-location : netvista\ndisfreetonpagedlookasidelist.htm
old-project : netvista
ms.assetid : 2405a405-177a-420a-9628-a340e0d0acb3
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : NdisFreeToNPagedLookasideList, ndis/NdisFreeToNPagedLookasideList, ndis_lookaside_ref_8c12e884-8f7b-4bcc-9631-2173003e4ef6.xml, netvista.ndisfreetonpagedlookasidelist, NdisFreeToNPagedLookasideList macro [Network Drivers Starting with Windows Vista]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Desktop
req.target-min-winverclnt : Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisFreeToNPagedLookasideList (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisFreeToNPagedLookasideList (NDIS 5.1)) in Windows XP.
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
req.irql : <= DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisFreeToNPagedLookasideList function
The 
  <b>NdisFreeToNPagedLookasideList</b> function returns an entry to the given lookaside list.

## Syntax

````
VOID NdisFreeToNPagedLookasideList(
  [in] PNPAGED_LOOKASIDE_LIST Lookaside,
  [in] PVOID                  Entry
);
````

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
    <mshelp:link keywords="netvista.ndisinitializenpagedlookasidelist" tabindex="0"><b>
    NdisInitializeNPagedLookasideList</b></mshelp:link> function, or it frees the given entry itself.

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

<mshelp:link keywords="netvista.ndisinitializenpagedlookasidelist" tabindex="0"><b>
   NdisInitializeNPagedLookasideList</b></mshelp:link>

<mshelp:link keywords="netvista.ndisallocatefromnpagedlookasidelist" tabindex="0"><b>
   NdisAllocateFromNPagedLookasideList</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFreeToNPagedLookasideList macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>