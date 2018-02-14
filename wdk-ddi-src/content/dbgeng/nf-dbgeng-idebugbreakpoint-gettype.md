---
UID: NF:dbgeng.IDebugBreakpoint.GetType
title: IDebugBreakpoint::GetType method
author: windows-driver-content
description: The GetType method returns the type of the breakpoint and the type of the processor that a breakpoint is set for.
old-location: debugger\gettype.htm
old-project: debugger
ms.assetid: c6aa6560-3183-4e3a-a625-80d1c5072af5
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetType method [Windows Debugging], IDebugBreakpoint2 interface, IDebugBreakpoint2::GetType, GetType method [Windows Debugging], IDebugBreakpoint2 interface [Windows Debugging], GetType method, IDebugBreakpoint interface [Windows Debugging], GetType method, dbgeng/IDebugBreakpoint::GetType, debugger.gettype, IDebugBreakpoint::GetType, dbgeng/IDebugBreakpoint2::GetType, IDebugBreakpoint, GetType, ComOther_3305c400-f816-463b-a643-4495bf546460.xml, GetType method [Windows Debugging], IDebugBreakpoint interface
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
-	IDebugBreakpoint.GetType
-	IDebugBreakpoint2.GetType
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetType method
The <b>GetType</b> method returns the type of the breakpoint and the type of the processor that a breakpoint is set for.

## Syntax

````
HRESULT GetType(
  [out] PULONG BreakType,
  [out] PULONG ProcType
);
````

## Parameters

`BreakType`

The type of the breakpoint.  The type can be one of the following  values.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_BREAKPOINT_CODE

</td>
<td>
Software breakpoint

</td>
</tr>
<tr>
<td>
DEBUG_BREAKPOINT_DATA

</td>
<td>
Processor breakpoint

</td>
</tr>
</table>

`ProcType`

The type of the processor that the breakpoint is set for.


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

If changes are made to the breakpoint, the processor type might change.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff548095">GetParameters</a> method also returns the information that is returned in <i>BreakType</i> and <i>ProcType</i>.

For more information about breakpoint types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538928">Breakpoints</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |