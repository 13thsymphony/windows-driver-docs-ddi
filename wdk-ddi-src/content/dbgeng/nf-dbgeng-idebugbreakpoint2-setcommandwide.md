---
UID: NF:dbgeng.IDebugBreakpoint2.SetCommandWide
title: IDebugBreakpoint2::SetCommandWide method
author: windows-driver-content
description: The SetCommandWide method sets the command that is executed when a breakpoint is triggered.
old-location: debugger\setcommandwide.htm
old-project: debugger
ms.assetid: 3edab087-01e4-4cd4-82d3-38d67962c93c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugBreakpoint2, IDebugBreakpoint2::SetCommandWide, SetCommandWide
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
req.alt-api: IDebugBreakpoint2.SetCommandWide
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugBreakpoint2::SetCommandWide method



## -description
The <b>SetCommandWide</b> method sets the command that is executed when a breakpoint is triggered.



## -syntax

````
HRESULT SetCommandWide(
  [in] PCWSTR Command
);
````


## -parameters

### -param Command [in]

The command string that is executed when the breakpoint is triggered.


## -returns
<b>SetCommandWide</b> might return one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


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