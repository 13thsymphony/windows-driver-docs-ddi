---
UID: NF:wdm.RtlAreBitsClear
title: RtlAreBitsClear function
author: windows-driver-content
description: The RtlAreBitsClear routine determines whether a given range of bits within a bitmap variable is clear.
old-location: kernel\rtlarebitsclear.htm
old-project: kernel
ms.assetid: f4092f06-3ed7-4153-8498-0fdfac958a1e
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlAreBitsClear, RtlAreBitsClear routine [Kernel-Mode Driver Architecture], k109_bbef7cb1-d817-498e-b091-2d07acc0e552.xml, kernel.rtlarebitsclear, wdm/RtlAreBitsClear
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
-	RtlAreBitsClear
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlAreBitsClear function
The <b>RtlAreBitsClear</b> routine determines whether a given range of bits within a bitmap variable is clear.

## Syntax

```
NTSYSAPI BOOLEAN RtlAreBitsClear(
  PRTL_BITMAP BitMapHeader,
  ULONG       StartingIndex,
  ULONG       Length
);
```

## Parameters

`BitMapHeader`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a> routine.

`StartingIndex`

Specifies the start of the bit range to be tested. This is a zero-based value indicating the position of the first bit in the range.

`Length`

Specifies how many bits to test.


## Return Value

<b>RtlAreBitsClear</b> returns <b>TRUE</b> if <i>Length </i>consecutive bits beginning at <i>StartingIndex</i> are clear (that is, all the bits from <i>StartingIndex </i>to (<i>StartingIndex </i>+ <i>Length</i>) -1). It returns <b>FALSE</b> if any bit in the given range is set, if the given range is not a proper subset of the bitmap, or if the given <i>Length</i> is zero.

## Remarks

Callers of <b>RtlAreBitsClear</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlAreBitsClear</b> can be called at any IRQL.

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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561745">RtlAreBitsSet</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561751">RtlCheckBit</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561755">RtlClearAllBits</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561873">RtlFindClearBits</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561877">RtlFindFirstRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561879">RtlFindLastBackwardRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561881">RtlFindLongestRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561885">RtlFindNextForwardRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a>