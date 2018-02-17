---
UID: NF:wdm.RtlCompareMemory
title: RtlCompareMemory function
author: windows-driver-content
description: The RtlCompareMemory routine compares two blocks of memory and returns the number of bytes that match.
old-location: kernel\rtlcomparememory.htm
old-project: kernel
ms.assetid: 1801fc27-53bf-4ac5-be41-072dfd8b0696
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlCompareMemory, kernel.rtlcomparememory, RtlCompareMemory routine [Kernel-Mode Driver Architecture], k109_3deee1b7-0b3a-4d24-8c0f-5e428d051a02.xml, wdm/RtlCompareMemory
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
req.ddi-compliance: BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctlA, BufAfterReqCompletedReadA, BufAfterReqCompletedWriteA
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib; OneCoreUAP.lib on Windows 10
req.dll: NtDll.dll (user mode); Kernel32.dll (user mode); NtosKrnl.exe (kernel mode)
req.irql: Any level (See Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtDll.dll
-	Kernel32.dll
-	NtosKrnl.exe
-	API-MS-Win-Core-rtlsupport-l1-1-0.dll
-	API-MS-Win-Core-rtlsupport-l1-2-0.dll
apiname:
-	RtlCompareMemory
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlCompareMemory function
The <b>RtlCompareMemory</b> routine compares two blocks of memory and returns the number of bytes that match.

## Syntax

````
SIZE_T RtlCompareMemory(
  _In_ const VOID   *Source1,
  _In_ const VOID   *Source2,
  _In_       SIZE_T Length
);
````

## Parameters

`Source1`

A pointer to the first block of memory.

`Source2`

A pointer to the second block of memory.

`Length`

The number of bytes to compare.


## Return Value

<b>RtlCompareMemory</b> returns the number of bytes in the two blocks that match. If all bytes match up to the specified <i>Length</i> value, the <i>Length</i> value is returned.

## Remarks

The routine starts by comparing the first byte in the first block to the first byte in the second block, and continues to compare successive bytes in the two blocks while the bytes match. The routine stops comparing bytes when it encounters the first pair of bytes that are not equal, or when the number of matching bytes equals the <i>Length</i> parameter value, whichever occurs first.

Callers of <b>RtlCompareMemory</b> can be running at any IRQL if both blocks of memory are resident.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib; OneCoreUAP.lib on Windows 10 |
| **DLL** | NtDll.dll (user mode); Kernel32.dll (user mode); NtosKrnl.exe (kernel mode) |
| **IRQL** | Any level (See Remarks section) |
| **DDI compliance rules** | BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctlA, BufAfterReqCompletedReadA, BufAfterReqCompletedWriteA |