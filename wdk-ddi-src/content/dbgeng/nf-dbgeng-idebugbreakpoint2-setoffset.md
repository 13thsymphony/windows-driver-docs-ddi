---
UID: NF:dbgeng.IDebugBreakpoint2.SetOffset
title: IDebugBreakpoint2::SetOffset method
author: windows-driver-content
description: The SetOffset method sets the location that triggers a breakpoint.
old-location: debugger\setoffset.htm
old-project: debugger
ms.assetid: 25898500-f16e-4838-854f-5eb299727e2b
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/IDebugBreakpoint::SetOffset, SetOffset, debugger.setoffset, ComOther_bb0d9a70-c4b5-4883-9dab-37bf04848d8c.xml, SetOffset method [Windows Debugging], IDebugBreakpoint::SetOffset, dbgeng/IDebugBreakpoint2::SetOffset, IDebugBreakpoint2, IDebugBreakpoint2 interface [Windows Debugging], SetOffset method, IDebugBreakpoint2::SetOffset, SetOffset method [Windows Debugging], IDebugBreakpoint interface, IDebugBreakpoint interface [Windows Debugging], SetOffset method, SetOffset method [Windows Debugging], IDebugBreakpoint2 interface
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
-	IDebugBreakpoint.SetOffset
-	IDebugBreakpoint2.SetOffset
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# SetOffset method
The <b>SetOffset</b> method sets the location that triggers a breakpoint.

## Syntax

````
HRESULT SetOffset(
  [in] ULONG64 Offset
);
````

## Parameters

`Offset`

The location on the target that triggers the breakpoint.


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
<dt><b>E_UNEXPECTED</b></dt>
</dl>
</td>
<td width="60%">
The breakpoint is deferred.

</td>
</tr>
</table> 

This method can also return other error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.

## Remarks

For more information about how to use breakpoints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |