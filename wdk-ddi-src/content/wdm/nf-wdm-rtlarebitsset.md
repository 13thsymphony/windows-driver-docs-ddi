---
UID: NF:wdm.RtlAreBitsSet
title: RtlAreBitsSet function
author: windows-driver-content
description: The RtlAreBitsSet routine determines whether a given range of bits within a bitmap variable is set.
old-location: kernel\rtlarebitsset.htm
old-project: kernel
ms.assetid: 7343f619-cf89-4768-b488-fe95f1da749d
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlAreBitsSet, RtlAreBitsSet routine [Kernel-Mode Driver Architecture], k109_8d2248d2-13e9-4f90-8d09-a3ea51579da8.xml, kernel.rtlarebitsset, wdm/RtlAreBitsSet
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
-	RtlAreBitsSet
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlAreBitsSet function
The <b>RtlAreBitsSet</b> routine determines whether a given range of bits within a bitmap variable is set.

## Syntax

```
NTSYSAPI BOOLEAN RtlAreBitsSet(
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

<b>RtlAreBitsSet</b> returns <b>TRUE</b> if <i>Length </i>consecutive bits beginning at <i>StartingIndex</i> are set (that is, all the bits from <i>StartingIndex </i>to (<i>StartingIndex </i>+ <i>Length</i>)). It returns <b>FALSE</b> if any bit in the given range is clear, if the given range is not a proper subset of the bitmap, or if the given <i>Length</i> is zero.

## Remarks

Callers of <b>RtlAreBitsSet</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlAreBitsSet</b> can be called at any IRQL.

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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561751">RtlCheckBit</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561890">RtlFindSetBits</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562770">RtlSetAllBits</a>