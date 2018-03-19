---
UID: NF:ntddk.MmFreeContiguousMemorySpecifyCache
title: MmFreeContiguousMemorySpecifyCache function
author: windows-driver-content
description: The MmFreeContiguousMemorySpecifyCache routine frees a buffer that was allocated by an MmAllocateContiguousMemorySpecifyCacheXxx routine.
old-location: kernel\mmfreecontiguousmemoryspecifycache.htm
old-project: kernel
ms.assetid: e5958dd7-b287-4f0d-8677-75d850885262
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: MmFreeContiguousMemorySpecifyCache, MmFreeContiguousMemorySpecifyCache routine [Kernel-Mode Driver Architecture], k106_256e3525-d48d-4045-872c-2e2fd6302525.xml, kernel.mmfreecontiguousmemoryspecifycache, wdm/MmFreeContiguousMemorySpecifyCache
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmFreeContiguousMemorySpecifyCache
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# MmFreeContiguousMemorySpecifyCache function
The <b>MmFreeContiguousMemorySpecifyCache</b> routine frees a buffer that was allocated by an <b>MmAllocateContiguousMemorySpecifyCache<i>Xxx</i></b> routine.

## Syntax

````
VOID MmFreeContiguousMemorySpecifyCache(
  _In_ PVOID               BaseAddress,
  _In_ SIZE_T              NumberOfBytes,
  _In_ MEMORY_CACHING_TYPE CacheType
);
````

## Parameters

`BaseAddress`

Specifies the base address of the buffer to be freed. Must match the address returned by the <b>MmAllocateContiguousMemorySpecifyCache<i>Xxx</i></b> call that allocated the buffer.

`NumberOfBytes`

Specifies the size in bytes of the buffer to be freed. Must match the size requested when the buffer was allocated by the <b>MmAllocateContiguousMemorySpecifyCache<i>Xxx</i></b> routine.

`CacheType`

Specifies the cache type of the buffer to be freed. Must match the cache type requested when the buffer was allocated by the <b>MmAllocateContiguousMemorySpecifyCache<i>Xxx</i></b> routine.


## Return Value

None

## Remarks

The <b>MmFreeContiguousMemorySpecifyCache</b> routine frees a block of physically contiguous memory that was allocated by a previous call to the <a href="..\wdm\nf-wdm-mmallocatecontiguousmemoryspecifycache.md">MmAllocateContiguousMemorySpecifyCache</a> or <a href="..\wdm\nf-wdm-mmallocatecontiguousmemoryspecifycachenode.md">MmAllocateContiguousMemorySpecifyCacheNode</a> routine. However, <a href="..\wdm\nf-wdm-mmfreecontiguousmemory.md">MmFreeContiguousMemory</a> is the preferred routine to use to free memory that was allocated by an <b>MmAllocateContiguousMemorySpecifyCache<i>Xxx</i></b> routine. <b>MmFreeContiguousMemory</b> is faster than <b>MmFreeContiguousMemorySpecifyCache</b> and requires fewer parameters.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Wdm.h, Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\wdm\nf-wdm-mmfreecontiguousmemory.md">MmFreeContiguousMemory</a>



<a href="..\wdm\nf-wdm-mmallocatecontiguousmemoryspecifycache.md">MmAllocateContiguousMemorySpecifyCache</a>



<a href="..\wdm\nf-wdm-mmallocatecontiguousmemoryspecifycachenode.md">MmAllocateContiguousMemorySpecifyCacheNode</a>