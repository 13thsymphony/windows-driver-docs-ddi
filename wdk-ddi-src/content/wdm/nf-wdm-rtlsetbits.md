---
UID: NF:wdm.RtlSetBits
title: RtlSetBits function
author: windows-driver-content
description: The RtlSetBits routine sets all bits in a given range of a given bitmap variable.
old-location: kernel\rtlsetbits.htm
old-project: kernel
ms.assetid: 63f796c1-033f-450a-a4da-527b8688448b
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlSetBits, RtlSetBits routine [Kernel-Mode Driver Architecture], k109_aca53733-c7f0-4c1a-9334-b7e27b199299.xml, kernel.rtlsetbits, wdm/RtlSetBits
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
-	RtlSetBits
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlSetBits function
The <b>RtlSetBits</b> routine sets all bits in a given range of a given bitmap variable.

## Syntax

```
NTSYSAPI VOID RtlSetBits(
  PRTL_BITMAP BitMapHeader,
  ULONG       StartingIndex,
  ULONG       NumberToSet
);
```

## Parameters

`BitMapHeader`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a> routine.

`StartingIndex`

Specifies the start of the bit range to be set. This is a zero-based value indicating the position of the first bit in the range.

`NumberToSet`

Specifies how many bits to set.


## Return Value

None

## Remarks

<b>RtlSetBits</b> simply returns control if the input <i>NumberToSet</i> is zero. <i>StartingIndex</i> plus <i>NumberToSet </i>must be less than or equal to <i>BitMapHeader</i>-&gt;<b>SizeOfBitMap</b>.

Callers of <b>RtlSetBits</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlSetBits</b> can be called at any IRQL.

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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561874">RtlFindClearBitsAndSet</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561875">RtlFindClearRuns</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561877">RtlFindFirstRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561879">RtlFindLastBackwardRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561881">RtlFindLongestRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561885">RtlFindNextForwardRunClear</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562034">RtlNumberOfClearBits</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562770">RtlSetAllBits</a>