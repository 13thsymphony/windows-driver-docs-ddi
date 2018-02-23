---
UID: NC:wdbgexts.PWINDBG_READ_PROCESS_MEMORY_ROUTINE
title: PWINDBG_READ_PROCESS_MEMORY_ROUTINE
author: windows-driver-content
description: The PWINDBG_READ_PROCESS_MEMORY_ROUTINE (ReadMemory) function works like the Win32 ReadProcessMemory function. It reads memory from the process being debugged. The entire area to be read must be accessible, or the operation fails.
old-location: debugger\readmemory.htm
old-project: Debugger
ms.assetid: 36169759-1ee3-4463-a381-67b0277cca25
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: debugger.readmemory, ReadMemory, ReadMemory callback function [Windows Debugging], ReadMemory, PWINDBG_READ_PROCESS_MEMORY_ROUTINE, PWINDBG_READ_PROCESS_MEMORY_ROUTINE, wdbgexts/ReadMemory, WdbgExts_Ref_53e869bc-03c9-4818-80fd-ca1bdafe2b96.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	wdbgexts.h
apiname:
-	ReadMemory
product: Windows
targetos: Windows
req.typenames: VPCI_WRITE_BLOCK_INPUT, *PVPCI_WRITE_BLOCK_INPUT
req.product: Windows 10 or later.
---


# PWINDBG_READ_PROCESS_MEMORY_ROUTINE callback function
The <b>PWINDBG_READ_PROCESS_MEMORY_ROUTINE</b> (<b>ReadMemory</b>) function works like the Win32 <b>ReadProcessMemory</b> function. It reads memory from the process being debugged. The entire area to be read must be accessible, or the operation fails.

## Syntax

```
PWINDBG_READ_PROCESS_MEMORY_ROUTINE PwindbgReadProcessMemoryRoutine;

ULONG PwindbgReadProcessMemoryRoutine(
  ULONG_PTR offset,
  PVOID lpBuffer,
  ULONG cb,
  PULONG lpcbBytesRead
)
{...}
```

## Parameters

`offset`

Specifies the base address of the memory to be read in the process that is being debugged.

`lpBuffer`

Points to the buffer to receive the memory read.

`cb`

Specifies the number of bytes that you want <b>ReadMemory</b> to read.

`lpcbBytesRead`

Receives the actual number of bytes that <b>ReadMemory</b> transferred into the buffer. This parameter is optional; if it is <b>NULL</b>, it is ignored.


## Return Value

If the routine succeeds, the return value is <b>TRUE</b>; otherwise, it is <b>FALSE</b>.

## Remarks

If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wdbgexts.h (include Wdbgexts.h, Dbgeng.h) |