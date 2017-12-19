---
UID: NF.dbgeng.IDebugBreakpoint2.SetCommand
title: IDebugBreakpoint2::SetCommand method
author: windows-driver-content
description: The SetCommand method sets the command that is executed when a breakpoint is triggered.
old-location: debugger\setcommand.htm
old-project: Debugger
ms.assetid: 0c9db77e-6e5d-45cd-a52c-dcc3acf5cba0
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IDebugBreakpoint2, IDebugBreakpoint2::SetCommand, SetCommand
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
req.alt-api: IDebugBreakpoint.SetCommand,IDebugBreakpoint2.SetCommand
req.alt-loc: dbgeng.h
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

# IDebugBreakpoint2::SetCommand method



## -description
The <b>SetCommand</b>  method sets the command that is executed when a breakpoint is triggered.



## -syntax

````
HRESULT SetCommand(
  [in] PCSTR Command
);
````


## -parameters

### -param Command [in]

The command string that is executed when the breakpoint is triggered.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.


## -remarks
The command string is a list of debugger commands that are separated by semicolons.  These commands are executed every time that the breakpoint is triggered.  The commands are executed before the engine informs any event callbacks that the breakpoint has been triggered.

If the command string includes an execution command such as <b>G (Go)</b>, this command should be the last command in the <i>Command</i> string.  If a command causes the target to resume execution, the rest of the command string is ignored.

For more information about breakpoint properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>