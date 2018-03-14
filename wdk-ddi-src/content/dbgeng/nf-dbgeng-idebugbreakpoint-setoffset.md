---
UID: NF:dbgeng.IDebugBreakpoint.SetOffset
title: IDebugBreakpoint::SetOffset method
author: windows-driver-content
description: The SetOffset method sets the location that triggers a breakpoint.
old-location: debugger\setoffset.htm
old-project: debugger
ms.assetid: 25898500-f16e-4838-854f-5eb299727e2b
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: ComOther_bb0d9a70-c4b5-4883-9dab-37bf04848d8c.xml, IDebugBreakpoint, IDebugBreakpoint interface [Windows Debugging], SetOffset method, IDebugBreakpoint2 interface [Windows Debugging], SetOffset method, IDebugBreakpoint2::SetOffset, IDebugBreakpoint::SetOffset, SetOffset method [Windows Debugging], SetOffset method [Windows Debugging], IDebugBreakpoint interface, SetOffset method [Windows Debugging], IDebugBreakpoint2 interface, SetOffset,IDebugBreakpoint.SetOffset, dbgeng/IDebugBreakpoint2::SetOffset, dbgeng/IDebugBreakpoint::SetOffset, debugger.setoffset
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
-	IDebugBreakpoint.SetOffset
-	IDebugBreakpoint2.SetOffset
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
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