---
UID: NF:ntifs.CcSetBcbOwnerPointer
title: CcSetBcbOwnerPointer function
author: windows-driver-content
description: The CcSetBcbOwnerPointer routine sets the owner thread pointer for a pinned buffer control block (BCB).
old-location: ifsk\ccsetbcbownerpointer.htm
old-project: ifsk
ms.assetid: fa99ebc4-72d3-42ef-9dda-dcfdd438f66f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CcSetBcbOwnerPointer, CcSetBcbOwnerPointer routine [Installable File System Drivers], ccref_9ad1d1a5-0600-4cfa-88d3-e4e5d2cd9df1.xml, ifsk.ccsetbcbownerpointer, ntifs/CcSetBcbOwnerPointer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	CcSetBcbOwnerPointer
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# CcSetBcbOwnerPointer function
The <b>CcSetBcbOwnerPointer</b> routine sets the owner thread pointer for a pinned buffer control block (BCB).

## Syntax

```
NTKERNELAPI VOID CcSetBcbOwnerPointer(
  PVOID Bcb,
  PVOID OwnerPointer
);
```

## Parameters

`Bcb`

Pointer to a pinned BCB structure that is owned by the current thread.

`OwnerPointer`

A valid resource owner pointer, which means a pointer to an allocated system address, with the low-order two bits set. This address may not be deallocated until after the BCB is unpinned by a subsequent call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539231">CcUnpinDataForThread</a>.


## Return Value

None

## Remarks

File systems call <b>CcSetBcbOwnerPointer</b> to set the resource owner for a pinned buffer control block (BCB), in cases where another thread will unpin the BCB and thus the current thread can exit.

Each call to <b>CcSetBcbOwnerPointer</b> must be matched by a subsequent call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539231">CcUnpinDataForThread</a>, which must be called with the same owner pointer.

BCBs that have been modified by <b>CcSetBcbOwnerPointer</b> cannot be unpinned by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff539228">CcUnpinData</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539228">CcUnpinData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539231">CcUnpinDataForThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545600">ExSetResourceOwnerPointer</a>