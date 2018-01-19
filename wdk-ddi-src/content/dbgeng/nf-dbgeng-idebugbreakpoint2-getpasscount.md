---
UID : NF:dbgeng.IDebugBreakpoint2.GetPassCount
title : IDebugBreakpoint2::GetPassCount method
author : windows-driver-content
description : The GetPassCount method returns the number of times that the target was originally required to reach the breakpoint location before the breakpoint is triggered.
old-location : debugger\getpasscount.htm
old-project : debugger
ms.assetid : d7abe2aa-a33c-4184-a850-d0efa1e99221
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : IDebugBreakpoint2, IDebugBreakpoint2::GetPassCount, GetPassCount
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
req.alt-api : IDebugBreakpoint.GetPassCount,IDebugBreakpoint2.GetPassCount
req.alt-loc : dbgeng.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetPassCount method
The <b>GetPassCount</b> method returns the number of times that the target was originally required to reach the breakpoint location before the breakpoint is triggered.

## Syntax

````
HRESULT GetPassCount(
  [out] PULONG Count
);
````

## Parameters

`Count`

The number of times that the target was originally required to hit the breakpoint before it is triggered.  The number of times that the target was originally required to pass the breakpoint without triggering it is the value that is returned to <i>Count</i>, minus one.


## Return Value

<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.

## Remarks

The <b>GetPassCount</b> method returns the number of hits that were originally required to trigger the breakpoint. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff545769">GetCurrentPassCount</a> method returns the number of hits that still must occur to trigger the breakpoint. For example, if a breakpoint was created with a pass count of 20, and there have been 5 passes so far, this method <b>GetPassCount</b> returns 20 and <b>GetCurrentPassCount</b> returns 15.

After the target has hit the breakpoint enough times to trigger it, the breakpoint is triggered every time that it is hit, unless you call <a href="https://msdn.microsoft.com/library/windows/hardware/ff556759">SetPassCount</a>.  You can also call <b>SetPassCount</b> to change the pass count before the breakpoint has been triggered. This call resets the original pass count and the remaining pass count.

If the debugger executes the code at the breakpoint location while stepping through the code, this execution does not contribute to the number of times that remain before the breakpoint is triggered.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff548095">GetParameters</a> method also returns the information that is returned in <i>Count</i>.

For more information about breakpoint properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |