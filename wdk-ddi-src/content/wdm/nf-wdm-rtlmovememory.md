---
UID: NF:wdm.RtlMoveMemory
title: RtlMoveMemory macro
author: windows-driver-content
description: The RtlMoveMemory routine copies the contents of a source memory block to a destination memory block, and supports overlapping source and destination memory blocks.
old-location: kernel\rtlmovememory.htm
old-project: kernel
ms.assetid: f6727247-e704-42d7-b4f1-ce7d20e317bb
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlMoveMemory, RtlMoveMemory routine [Kernel-Mode Driver Architecture], k109_5731ba5b-a7a5-4883-87cf-543768a29a93.xml, kernel.rtlmovememory, wdm/RtlMoveMemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctlA, BufAfterReqCompletedReadA, BufAfterReqCompletedWriteA
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level (See Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlMoveMemory
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlMoveMemory function
The <b>RtlMoveMemory</b> routine copies the contents of a source memory block to a destination memory block, and supports overlapping source and destination memory blocks.

## Syntax

````
VOID RtlMoveMemory(
  _Out_       VOID UNALIGNED *Destination,
  _In_  const VOID UNALIGNED *Source,
  _In_        SIZE_T         Length
);
````

## Parameters

`Destination`

A pointer to the destination memory block to copy the bytes to.

`Source`

A pointer to the source memory block to copy the bytes from.

`Length`

The number of bytes to copy from the source to the destination.


## Return Value

None

## Remarks

The source memory block, which is defined by <i>Source</i> and <i>Length</i>, can overlap the destination memory block, which is defined by <i>Destination</i> and <i>Length</i>.

The <a href="..\wdm\nf-wdm-rtlcopymemory.md">RtlCopyMemory</a> routine runs faster than <b>RtlMoveMemory</b>, but <b>RtlCopyMemory</b> requires that the source and destination memory blocks do not overlap.

Callers of <b>RtlMoveMemory</b> can be running at any IRQL if the source and destination memory blocks are in nonpaged system memory. Otherwise, the caller must be running at IRQL &lt;= APC_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level (See Remarks section) |
| **DDI compliance rules** | BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctlA, BufAfterReqCompletedReadA, BufAfterReqCompletedWriteA |

## See Also

<a href="..\wdm\nf-wdm-rtlcopymemory.md">RtlCopyMemory</a>