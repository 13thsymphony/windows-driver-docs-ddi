---
UID : NF:dbgeng.IDebugBreakpoint2.SetCommandWide
title : IDebugBreakpoint2::SetCommandWide method
author : windows-driver-content
description : The SetCommandWide method sets the command that is executed when a breakpoint is triggered.
old-location : debugger\setcommandwide.htm
old-project : debugger
ms.assetid : 3edab087-01e4-4cd4-82d3-38d67962c93c
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : debugger.setcommandwide, SetCommandWide method [Windows Debugging], IDebugBreakpoint2 interface, IDebugBreakpoint2::SetCommandWide, IDebugBreakpoint2, dbgeng/IDebugBreakpoint2::SetCommandWide, SetCommandWide, IDebugBreakpoint2 interface [Windows Debugging], SetCommandWide method, SetCommandWide method [Windows Debugging]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : dbgeng.h
req.include-header : Dbgeng.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : dbgeng.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# SetCommandWide method
The <b>SetCommandWide</b> method sets the command that is executed when a breakpoint is triggered.

## Syntax

````
HRESULT SetCommandWide(
  [in] PCWSTR Command
);
````

## Parameters

`Command`

The command string that is executed when the breakpoint is triggered.


## Return Value

<b>SetCommandWide</b> might return one of the following values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>

## Remarks

The command string is a list of debugger commands that are separated by semicolons.  These commands are executed every time that the breakpoint is triggered.  The commands are executed before the engine informs any event callbacks that the breakpoint has been triggered.

If the command string includes an execution command such as <b>G (Go)</b>, this command should be the last command in the <i>Command</i> string.  If a command causes the target to resume execution, the rest of the command string is ignored.

For more information about breakpoint properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |