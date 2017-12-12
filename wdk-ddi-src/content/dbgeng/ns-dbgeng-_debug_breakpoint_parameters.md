---
UID: NS.DBGENG._DEBUG_BREAKPOINT_PARAMETERS
title: _DEBUG_BREAKPOINT_PARAMETERS
author: windows-driver-content
description: The DEBUG_BREAKPOINT_PARAMETERS structure contains most of the parameters for describing a breakpoint.
old-location: debugger\debug_breakpoint_parameters.htm
old-project: debugger
ms.assetid: e5c87c1c-8195-4476-84bc-5f18ad83d149
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DEBUG_BREAKPOINT_PARAMETERS, *PDEBUG_BREAKPOINT_PARAMETERS, DEBUG_BREAKPOINT_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dbgeng.h
req.include-header: DbgEng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DEBUG_BREAKPOINT_PARAMETERS
req.alt-loc: DbgEng.h
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
---

# _DEBUG_BREAKPOINT_PARAMETERS structure



## -description
The DEBUG_BREAKPOINT_PARAMETERS structure contains most of the parameters for describing a breakpoint.



## -syntax

````
typedef struct _DEBUG_BREAKPOINT_PARAMETERS {
  ULONG64 Offset;
  ULONG   Id;
  ULONG   BreakType;
  ULONG   ProcType;
  ULONG   Flags;
  ULONG   DataSize;
  ULONG   DataAccessType;
  ULONG   PassCount;
  ULONG   CurrentPassCount;
  ULONG   MatchThread;
  ULONG   CommandSize;
  ULONG   OffsetExpressionSize;
} DEBUG_BREAKPOINT_PARAMETERS, *PDEBUG_BREAKPOINT_PARAMETERS;
````


## -struct-fields

### -field Offset

The location in the target's memory address space that will trigger the breakpoint.  If the breakpoint is deferred (see <a href="debugger.getflags">GetFlags</a>), <b>Offset</b> is DEBUG_INVALID_OFFSET.  See <a href="debugger.getoffset">GetOffset</a>.


### -field Id

The breakpoint ID.  See <a href="debugger.getid">GetId</a>.


### -field BreakType

Specifies if the breakpoint is a software breakpoint or a processor breakpoint.  See <a href="debugger.gettype">GetType</a>.


### -field ProcType

The processor type for which the breakpoint is set.  See <a href="debugger.gettype">GetType</a>.


### -field Flags

The flags for the breakpoint.  See <a href="debugger.getflags">GetFlags</a>.


### -field DataSize

The size, in bytes, of the memory block whose access will trigger the breakpoint.  If the type of the breakpoint is not a data breakpoint, this is zero.  See <a href="debugger.getdataparameters">GetDataParameters</a>.


### -field DataAccessType

The type of access that will trigger the breakpoint.  If the type of the breakpoint is not a data breakpoint, this is zero.  See <a href="debugger.getdataparameters">GetDataParameters</a>.


### -field PassCount

The number of times the target will hit the breakpoint before it is triggered.  See <a href="debugger.getpasscount">GetPassCount</a>.


### -field CurrentPassCount

The remaining number of times that the target will hit the breakpoint before it is triggered.  See <a href="debugger.getcurrentpasscount">GetCurrentPassCount</a>.


### -field MatchThread

The engine thread ID of the thread that can trigger this breakpoint.  If any thread can trigger this breakpoint, <b>MatchThread</b> is DEBUG_ANY_ID.  See <a href="debugger.getmatchthreadid">GetMatchThreadId</a>.


### -field CommandSize

The size, in characters, of the command string that will be executed when the breakpoint is triggered.  If no command is set, <b>CommandSize</b> is zero.  See <a href="debugger.getcommand">GetCommand</a>.


### -field OffsetExpressionSize

The size, in characters, of the expression string that evaluates to the location in the target's memory address space where the breakpoint is triggered.  If no expression string is set, <b>OffsetExpressionSize</b> is zero.  See <a href="debugger.getoffsetexpression">GetOffsetExpression</a>.


## -remarks
For an overview of how to use breakpoints, and a description of all breakpoint-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538928">Breakpoints</a>.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>DbgEng.h (include DbgEng.h)</dt>
</dl>
</td>
</tr>
</table>