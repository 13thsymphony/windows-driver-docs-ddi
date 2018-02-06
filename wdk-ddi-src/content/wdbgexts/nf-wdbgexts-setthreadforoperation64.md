---
UID: NF:wdbgexts.SetThreadForOperation64
title: SetThreadForOperation64 function
author: windows-driver-content
description: The SetThreadForOperation64 function sets the thread to use for the next StackTrace call.
old-location: debugger\setthreadforoperation64.htm
old-project: debugger
ms.assetid: 0c8f7113-0866-454a-9596-8733dd78b282
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: SetThreadForOperation64 function [Windows Debugging], debugger.setthreadforoperation64, SetThreadForOperation64, wdbgexts/SetThreadForOperation64, WdbgExts_Ref_8c7ef2e9-4096-4284-9878-63d90f49e227.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdbgexts.h
apiname:
-	SetThreadForOperation64
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---


# SetThreadForOperation64 function
The <b>SetThreadForOperation64</b> function sets the thread to use for the next <a href="..\wdbgexts\nc-wdbgexts-pwindbg_stacktrace_routine.md">StackTrace</a> call.

## Syntax

````
__inline VOID SetThreadForOperation64(
   PULONG64 Thread
);
````

## Parameters

`Thread`

Points to the thread object to be used for the next stack trace.


## Return Value

None

## Remarks

If you are writing 32-bit code, you should use <a href="..\wdbgexts\nf-wdbgexts-setthreadforoperation.md">SetThreadForOperation</a> instead. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff537780">32-Bit Pointers and 64-Bit Pointers</a> for details.

For a WdbgExts extension, include Wdbgexts.h. For a DbgEng extension, include Wdbgexts.h before Dbgeng.h. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wdbgexts.h (include Wdbgexts.h, Dbgeng.h) |
| **Library** | NtosKrnl.exe |