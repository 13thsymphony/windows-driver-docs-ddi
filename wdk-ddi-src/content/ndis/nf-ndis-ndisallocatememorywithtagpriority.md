---
UID: NF:ndis.NdisAllocateMemoryWithTagPriority
title: NdisAllocateMemoryWithTagPriority function
author: windows-driver-content
description: NDIS drivers call the NdisAllocateMemoryWithTagPriority function to allocate a pool of memory from the non-paged pool.
old-location: netvista\ndisallocatememorywithtagpriority.htm
old-project: netvista
ms.assetid: aac4049c-a876-4bbb-ba3b-fa36c299e1c7
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisAllocateMemoryWithTagPriority, NdisAllocateMemoryWithTagPriority function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateMemoryWithTagPriority, ndis_memory_ref_1b725109-fc0d-4f5f-8c88-d7a21a1f4c01.xml, netvista.ndisallocatememorywithtagpriority
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
req.ddi-compliance: Irql_Miscellaneous_Function, NdisAllocateMemoryWithTagPriority
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
-	NdisAllocateMemoryWithTagPriority
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisAllocateMemoryWithTagPriority function
NDIS drivers call the 
  <b>NdisAllocateMemoryWithTagPriority</b> function to allocate a pool of memory from the non-paged
  pool.

## Syntax

````
PVOID NdisAllocateMemoryWithTagPriority(
  _In_ NDIS_HANDLE      NdisHandle,
  _In_ UINT             Length,
  _In_ ULONG            Tag,
  _In_ EX_POOL_PRIORITY Priority
);
````

## Parameters

`NdisHandle`

An NDIS handle that the caller obtained during initialization. For example, a miniport driver can
     use the NDIS handle that it obtained from the 
     <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
     NdisMRegisterMiniportDriver</a> or 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function.
     Other NDIS drivers can use the handles from the following functions:
     


<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a>



<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">NdisFRegisterFilterDriver</a>



<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>

`Length`

The size to be allocated, in bytes.

`Tag`

A string, delimited by single quotation marks, with up to four characters, usually specified in
     reversed order. The NDIS-supplied default tag for this call is 'maDN', but the caller can override this
     default by supplying an explicit value.

`Priority`

The importance of this request. For more information, see 
     <a href="..\wdm\nf-wdm-exallocatepoolwithtagpriority.md">
     ExAllocatePoolWithTagPriority</a>.


## Return Value

<b>NdisAllocateMemoryWithTagPriority</b> returns a pointer to a base virtual address of the allocated
     memory, or <b>NULL</b> if sufficient nonpaged memory is currently unavailable.

## Remarks

To free memory that was allocated with 
    <b>NdisAllocateMemoryWithTagPriority</b>, call the 
    <a href="..\ndis\nf-ndis-ndisfreememorywithtagpriority.md">NdisFreeMemoryWithTagPriority</a> or <a href="..\ndis\nf-ndis-ndisfreememory.md">NdisFreeMemory</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_Miscellaneous_Function, NdisAllocateMemoryWithTagPriority |

## See Also

<a href="..\wdm\nf-wdm-exallocatepoolwithtagpriority.md">ExAllocatePoolWithTagPriority</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550767">NdisAllocateMemoryWithTag</a>



<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>



<a href="..\ndis\nf-ndis-ndisfreememory.md">NdisFreeMemory</a>



<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a>



<a href="..\ndis\nf-ndis-ndisfreememorywithtagpriority.md">NdisFreeMemoryWithTagPriority</a>



<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">NdisFRegisterFilterDriver</a>