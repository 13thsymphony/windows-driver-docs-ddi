---
UID: NF:ndis.NdisFreeRWLock
title: NdisFreeRWLock function
author: windows-driver-content
description: The NdisFreeRWLock function frees a read/write lock that was previously allocated with the NdisAllocateRWLock function.
old-location: netvista\ndisfreerwlock.htm
old-project: netvista
ms.assetid: 1f54e8fe-e6a2-4ddd-9451-289d3df21fde
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisFreeRWLock, NdisFreeRWLock function [Network Drivers Starting with Windows Vista], ndis/NdisFreeRWLock, ndis_processor_group_ref_f711221a-f265-446e-86bc-7b5b4d17f7d9.xml, netvista.ndisfreerwlock
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisFreeRWLock
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisFreeRWLock function
The 
  <b>NdisFreeRWLock</b> function frees a read/write lock that was previously allocated with the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff561615">NdisAllocateRWLock</a> function.

## Syntax

```
void NdisFreeRWLock(
  __drv_freesMem(ndisrwlockex)PNDIS_RW_LOCK_EX Lock
);
```

## Parameters

`Lock`

A pointer to an opaque 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> variable that represents a
     lock. The caller can use this lock to gain write or read access to resources that are shared among
     non-ISR driver threads.


## Return Value

None

## Remarks

NDIS drivers call the 
    <b>NdisFreeRWLock</b> function to free the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a> structure and any associated
    resources that were previously allocated with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561615">NdisAllocateRWLock</a> function.

A driver must call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564523">NdisReleaseRWLock</a> function to release a
    read/write lock before it calls the 
    <b>NdisFreeRWLock</b> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.20 and later.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567279">NDIS_RW_LOCK_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561615">NdisAllocateRWLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564523">NdisReleaseRWLock</a>