---
UID: NF:dbgeng.IDebugBreakpoint.SetCommand
title: IDebugBreakpoint::SetCommand method
author: windows-driver-content
description: The SetCommand method sets the command that is executed when a breakpoint is triggered.
old-location: debugger\setcommand.htm
old-project: Debugger
ms.assetid: 0c9db77e-6e5d-45cd-a52c-dcc3acf5cba0
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugBreakpoint::SetCommand, SetCommand method [Windows Debugging], IDebugBreakpoint2 interface, IDebugBreakpoint2 interface [Windows Debugging], SetCommand method, ComOther_166ee15d-c9e1-466f-9337-a6d20e9355ee.xml, IDebugBreakpoint2::SetCommand, SetCommand method [Windows Debugging], SetCommand method [Windows Debugging], IDebugBreakpoint interface, IDebugBreakpoint, dbgeng/IDebugBreakpoint2::SetCommand, IDebugBreakpoint interface [Windows Debugging], SetCommand method, SetCommand, debugger.setcommand, dbgeng/IDebugBreakpoint::SetCommand
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugBreakpoint.SetCommand
-	IDebugBreakpoint2.SetCommand
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# SetCommand method
The <b>SetCommand</b>  method sets the command that is executed when a breakpoint is triggered.

## Syntax

````
HRESULT SetCommand(
  [in] PCSTR Command
);
````

## Parameters

`Command`

The command string that is executed when the breakpoint is triggered.


## Return Value

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
 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.

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