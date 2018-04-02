---
UID: NF:wdm.RtlFindNextForwardRunClear
title: RtlFindNextForwardRunClear function
author: windows-driver-content
description: The RtlFindNextForwardRunClear routine searches a given bitmap variable for the next clear run of bits, starting from the specified index position.
old-location: kernel\rtlfindnextforwardrunclear.htm
old-project: kernel
ms.assetid: d923c1a4-4715-4632-8c75-0e48dda9a210
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlFindNextForwardRunClear, RtlFindNextForwardRunClear routine [Kernel-Mode Driver Architecture], k109_3625ede2-f1b5-495d-9b79-2063e0daa567.xml, kernel.rtlfindnextforwardrunclear, wdm/RtlFindNextForwardRunClear
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
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL (See Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlFindNextForwardRunClear
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlFindNextForwardRunClear function
The <b>RtlFindNextForwardRunClear</b> routine searches a given bitmap variable for the next clear run of bits, starting from the specified index position.

## Syntax

```
NTSYSAPI ULONG RtlFindNextForwardRunClear(
  PRTL_BITMAP BitMapHeader,
  ULONG       FromIndex,
  PULONG      StartingRunIndex
);
```

## Parameters

`BitMapHeader`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a> routine.

`FromIndex`

Specifies a zero-based bit position at which to start looking for a clear run of bits.

`StartingRunIndex`

Pointer to a variable in which the starting index of the clear run found in the bitmap is returned. This is a zero-based value indicating the bit position of the first clear bit in the run. Its value is meaningless if <b>RtlFindNextForwardRunClear</b> cannot find a run of clear bits.


## Return Value

<b>RtlFindNextForwardRunClear</b> returns either the number of bits in the run beginning at <i>StartingRunIndex</i>, or zero if it cannot find a run of clear bits following <i>FromIndex</i> in the bitmap.

## Remarks

Callers of <b>RtlFindNextForwardRunClear</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlFindNextForwardRunClear</b> can be called at any IRQL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL (See Remarks section)" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561742">RtlAreBitsClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561873">RtlFindClearBits</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561875">RtlFindClearRuns</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561877">RtlFindFirstRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561879">RtlFindLastBackwardRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561881">RtlFindLongestRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a>