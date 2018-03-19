---
UID: NF:ntifs.RtlFillMemoryUlonglong
title: RtlFillMemoryUlonglong macro
author: windows-driver-content
description: The RtlFillMemoryUlonglong routine fills a given range of memory with one or more repetitions of a given ULONGLONG value.
old-location: ifsk\rtlfillmemoryulonglong.htm
old-project: ifsk
ms.assetid: b5604cdb-084e-431a-b413-020e8213a18f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlFillMemoryUlonglong, RtlFillMemoryUlonglong routine [Installable File System Drivers], ifsk.rtlfillmemoryulonglong, ntifs/RtlFillMemoryUlonglong, rtlref_5e06d1be-accd-40f6-a5b1-2a3b39caacce.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: For AMD64 systems, this routine is available on Microsoft Windows 2000 and later. For non-AMD64 systems, this routine is available on Windows 7 and later.
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlFillMemoryUlonglong
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlFillMemoryUlonglong function
The <b>RtlFillMemoryUlonglong</b> routine fills a given range of memory with one or more repetitions of a given ULONGLONG value.

## Syntax

````
VOID RtlFillMemoryUlonglong(
  _Out_ PVOID     Destination,
  _In_  SIZE_T    Length,
  _In_  ULONGLONG Pattern
);
````

## Parameters

`Destination`

Pointer to the start of the range of memory to be filled. This address must be ULONGLONG-aligned.

`Length`

Number of bytes to fill. This value must be a multiple of <b>sizeof(</b>ULONGLONG<b>)</b>. (Note: SIZE_T is defined in <i>basetsd.h</i>.)

`Pattern`

ULONGLONG value with which to fill the range starting at <i>Destination</i> and extending for <i>Length</i> bytes.


## Return Value

None

## Remarks

If the range of memory starting at <i>Destination</i> is nonpaged, the caller can be running at any IRQL. Otherwise, callers of <b>RtlFillMemoryUlonglong</b> must be running at IRQL &lt; DISPATCH_LEVEL.

For more information about managing buffered data and initializing driver-allocated buffers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540656">Buffered Data and Buffer Initialization</a>. 

For AMD64 systems, this routine is a macro.  For non-AMD64 systems, this routine is contained in Ntoskrnl.lib.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | For AMD64 systems, this routine is available on Microsoft Windows 2000 and later. For non-AMD64 systems, this routine is available on Windows 7 and later.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h, FltKernel.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | See Remarks section. |

## See Also

<a href="..\ntifs\nf-ntifs-rtlfillmemoryulong.md">RtlFillMemoryUlong</a>



<a href="..\wdm\nf-wdm-rtlfillmemory.md">RtlFillMemory</a>



<a href="..\wdm\nf-wdm-rtlzeromemory.md">RtlZeroMemory</a>