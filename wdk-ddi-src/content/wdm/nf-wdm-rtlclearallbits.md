---
UID: NF:wdm.RtlClearAllBits
title: RtlClearAllBits function
author: windows-driver-content
description: The RtlClearAllBits routine sets all bits in a given bitmap variable to zero.
old-location: kernel\rtlclearallbits.htm
old-project: kernel
ms.assetid: 8271b13a-a64e-4d5e-b319-283255b8127f
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlClearAllBits, RtlClearAllBits routine [Kernel-Mode Driver Architecture], k109_6fb17a55-6839-411c-9289-720657ba4983.xml, kernel.rtlclearallbits, wdm/RtlClearAllBits
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: "<= APC_LEVEL (See Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	Ntdll.dll
api_name:
-	RtlClearAllBits
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlClearAllBits function
The <b>RtlClearAllBits</b> routine sets all bits in a given bitmap variable to zero.

## Syntax

```
NTSYSAPI VOID RtlClearAllBits(
  PRTL_BITMAP BitMapHeader
);
```

## Parameters

`BitMapHeader`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a> routine.


## Return Value

None

## Remarks

Callers of <b>RtlClearAllBits</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlClearAllBits</b> can be called at any IRQL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe (kernel mode); Ntdll.dll (user mode) |
| **IRQL** | "<= APC_LEVEL (See Remarks section)" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561742">RtlAreBitsClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561745">RtlAreBitsSet</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561763">RtlClearBits</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561890">RtlFindSetBits</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561895">RtlFindSetBitsAndClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562037">RtlNumberOfSetBits</a>