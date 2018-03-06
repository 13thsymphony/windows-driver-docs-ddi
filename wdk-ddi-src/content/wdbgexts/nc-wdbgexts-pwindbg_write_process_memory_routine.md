---
UID: NC:wdbgexts.PWINDBG_WRITE_PROCESS_MEMORY_ROUTINE
title: PWINDBG_WRITE_PROCESS_MEMORY_ROUTINE
author: windows-driver-content
description: The PWINDBG_WRITE_PROCESS_MEMORY_ROUTINE (WriteMemory) function works like the Win32 WriteProcessMemory routine. It writes memory to the process being debugged. The entire area to be written must be accessible, or the operation fails.
old-location: debugger\writememory.htm
old-project: debugger
ms.assetid: 9e734d5d-736b-48cb-9635-f27006dd00e0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PWINDBG_WRITE_PROCESS_MEMORY_ROUTINE, WdbgExts_Ref_72933b84-f8ce-432e-b89c-09c2668aa90e.xml, WriteMemory, WriteMemory callback function [Windows Debugging], debugger.writememory, wdbgexts/WriteMemory
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wdbgexts.h
api_name:
-	WriteMemory
product: Windows
targetos: Windows
req.typenames: VPCI_WRITE_BLOCK_INPUT, *PVPCI_WRITE_BLOCK_INPUT
req.product: Windows 10 or later.
---


# PWINDBG_WRITE_PROCESS_MEMORY_ROUTINE callback function
The <b>PWINDBG_WRITE_PROCESS_MEMORY_ROUTINE</b> (<b>WriteMemory</b>) function works like the Win32 <b>WriteProcessMemory</b> routine. It writes memory to the process being debugged. The entire area to be written must be accessible, or the operation fails.

## Syntax

```
PWINDBG_WRITE_PROCESS_MEMORY_ROUTINE PwindbgWriteProcessMemoryRoutine;

ULONG PwindbgWriteProcessMemoryRoutine(
  ULONG_PTR offset,
  LPCVOID lpBuffer,
  ULONG cb,
  PULONG lpcbBytesWritten
)
{...}
```

## Parameters

`offset`

Specifies the base address of the memory to be written in the process that is being debugged.

`lpBuffer`



`cb`

Specifies the number of bytes that <b>WriteMemory</b> should write.

`lpcbBytesWritten`

Receives the actual number of bytes that <b>WriteMemory</b> transferred from the buffer. This parameter is optional; if it is <b>NULL</b>, it is ignored.


## Return Value

If the routine succeeds, the return value is <b>TRUE</b>; otherwise, it is <b>FALSE</b>.

## Remarks

For a WdbgExts extension, include wdbgexts.h. For a DbgEng extension, include wdbgexts.h before dbgeng.h. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wdbgexts.h (include Wdbgexts.h, Dbgeng.h) |