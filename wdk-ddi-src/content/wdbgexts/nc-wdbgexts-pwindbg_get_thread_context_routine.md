---
UID: NC:wdbgexts.PWINDBG_GET_THREAD_CONTEXT_ROUTINE
title: PWINDBG_GET_THREAD_CONTEXT_ROUTINE
author: windows-driver-content
description: The PWINDBG_GET_THREAD_CONTEXT_ROUTINE (GetContext) function implements the functionality that is similar to the Microsoft Win32 GetThreadContext routine. It returns the context of the process being debugged.
old-location: debugger\getcontext.htm
old-project: Debugger
ms.assetid: 706e05ae-9507-4414-b02c-52016e7bbbd9
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: debugger.getcontext, GetContext, GetContext callback function [Windows Debugging], GetContext, PWINDBG_GET_THREAD_CONTEXT_ROUTINE, PWINDBG_GET_THREAD_CONTEXT_ROUTINE, wdbgexts/GetContext, WdbgExts_Ref_52639fac-abbf-4abc-a01f-361d14e49fd0.xml
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
-	GetContext
product: Windows
targetos: Windows
req.typenames: VPCI_WRITE_BLOCK_INPUT, *PVPCI_WRITE_BLOCK_INPUT
req.product: Windows 10 or later.
---


# PWINDBG_GET_THREAD_CONTEXT_ROUTINE callback function
The <b>PWINDBG_GET_THREAD_CONTEXT_ROUTINE</b> (<b>GetContext</b>) function implements the functionality that is similar to the Microsoft Win32 <b>GetThreadContext</b> routine. It returns the context of the process being debugged.

## Syntax

```
PWINDBG_GET_THREAD_CONTEXT_ROUTINE PwindbgGetThreadContextRoutine;

ULONG PwindbgGetThreadContextRoutine(
  ULONG Processor,
  PCONTEXT lpContext,
  ULONG cbSizeOfContext
)
{...}
```

## Parameters

`Processor`



`lpContext`

Points to the address of a context structure that receives the appropriate context of the process being debugged. The context structure is highly machine-specific.

`cbSizeOfContext`

Specifies the size of the context structure.


## Return Value

If the routine succeeds, the return value is <b>TRUE</b>; otherwise, it is <b>FALSE</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wdbgexts.h (include Wdbgexts.h, Dbgeng.h) |