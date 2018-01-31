---
UID : NF:dbgeng.IDebugBreakpoint2.SetOffsetExpressionWide
title : IDebugBreakpoint2::SetOffsetExpressionWide method
author : windows-driver-content
description : The SetOffsetExpressionWide methods set an expression string that evaluates to the location that triggers a breakpoint.
old-location : debugger\setoffsetexpressionwide.htm
old-project : debugger
ms.assetid : 1db89a5a-641b-4fca-bd60-217c9be8f19f
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : IDebugBreakpoint2, SetOffsetExpressionWide, IDebugBreakpoint2::SetOffsetExpressionWide, SetOffsetExpressionWide method [Windows Debugging], IDebugBreakpoint2 interface, dbgeng/IDebugBreakpoint2::SetOffsetExpressionWide, SetOffsetExpressionWide method [Windows Debugging], debugger.setoffsetexpressionwide, IDebugBreakpoint2 interface [Windows Debugging], SetOffsetExpressionWide method
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


# SetOffsetExpressionWide method
The <b>SetOffsetExpressionWide</b> methods set an expression string that evaluates to the location that triggers a breakpoint.

## Syntax

````
HRESULT SetOffsetExpressionWide(
  [in] PCWSTR Expression
);
````

## Parameters

`Expression`

The expression string that evaluates to the location on the target that triggers the breakpoint.  If the engine scannot evaluate the expression (for example, if the expression contains a symbol that cannot be interpreted), the breakpoint is flagged as deferred. (For more information about deferred breakpoints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.)  For more information about the expression syntax, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>.


## Return Value

This method might return one of the following values:
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

For more information about how to use breakpoints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>.

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