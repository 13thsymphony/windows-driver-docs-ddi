---
UID: NF:dbgeng.IDebugBreakpoint2.GetCommand
title: IDebugBreakpoint2::GetCommand method
author: windows-driver-content
description: The GetCommand method returns the command string that is executed when a breakpoint is triggered.
old-location: debugger\getcommand.htm
old-project: debugger
ms.assetid: 3f7b704f-be73-459a-bb5a-bbe649751900
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: ComOther_4bb08d44-5a99-4177-b8a4-8926f1e45dcf.xml, GetCommand method [Windows Debugging], GetCommand method [Windows Debugging], IDebugBreakpoint interface, GetCommand method [Windows Debugging], IDebugBreakpoint2 interface, GetCommand,IDebugBreakpoint2.GetCommand, IDebugBreakpoint interface [Windows Debugging], GetCommand method, IDebugBreakpoint2, IDebugBreakpoint2 interface [Windows Debugging], GetCommand method, IDebugBreakpoint2::GetCommand, IDebugBreakpoint::GetCommand, dbgeng/IDebugBreakpoint2::GetCommand, dbgeng/IDebugBreakpoint::GetCommand, debugger.getcommand
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugBreakpoint.GetCommand
-	IDebugBreakpoint2.GetCommand
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetCommand method
The <b>GetCommand</b>  method returns the command string that is executed when a breakpoint is triggered.

## Syntax

````
HRESULT GetCommand(
  [out, optional] PSTR   Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG CommandSize
);
````

## Parameters

`Buffer`

The command string that is executed when the breakpoint is triggered.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

`BufferSize`

The size, in characters, of the buffer that <i>Buffer</i> points to.

`CommandSize`

The size of the command string.  If <i>CommandSize</i> is <b>NULL</b>, this information is not returned.


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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful, but the buffer was not large enough to hold the command string and so the command string was truncated to fit.

</td>
</tr>
</table>
 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.

## Remarks

The command string is a list of debugger commands that are separated by semicolons.  These commands are executed every time that the breakpoint is triggered.  The commands are executed before the engine informs any event callbacks that the breakpoint has been triggered.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff548095">GetParameters</a> method also returns the size of the breakpoint's command, <i>CommandSize</i>.

For more information about breakpoint properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |