---
UID: NF:dbgeng.IDebugControl3.SetExpressionSyntax
title: IDebugControl3::SetExpressionSyntax method
author: windows-driver-content
description: The SetExpressionSyntax method sets the syntax that the engine will use to evaluate expressions.
old-location: debugger\setexpressionsyntax.htm
old-project: debugger
ms.assetid: ab98312f-0240-498f-992a-b05cbcc64c04
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugControl3, IDebugControl3 interface [Windows Debugging], SetExpressionSyntax method, IDebugControl3::SetExpressionSyntax, IDebugControl_6f1ebcec-908b-4f00-b9cf-e7a036bc05e5.xml, SetExpressionSyntax method [Windows Debugging], SetExpressionSyntax method [Windows Debugging], IDebugControl3 interface, SetExpressionSyntax,IDebugControl3.SetExpressionSyntax, dbgeng/IDebugControl3::SetExpressionSyntax, debugger.setexpressionsyntax
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
-	IDebugControl3.SetExpressionSyntax
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# SetExpressionSyntax method
The <b>SetExpressionSyntax</b> method sets the syntax that the engine will use to evaluate expressions.

## Syntax

````
HRESULT SetExpressionSyntax(
  [in] ULONG Flags
);
````

## Parameters

`Flags`

Specifies the syntax that the engine will use to evaluate expressions.  It can be one of the following values:





#### DEBUG_EXPR_MASM

Expressions will be evaluated according to MASM syntax. For details of this syntax, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552157">MASM Numbers and Operators</a>.



#### DEBUG_EXPR_CPLUSPLUS

Expressions will be evaluated according to C++ syntax. For details of this syntax, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540372">C++ Numbers and Operators</a>.


## Return Value

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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

The expression syntax is a global setting within the engine, so setting the expression syntax will affect all clients.

The expression syntax of the engine determines how the engine will interpret expressions passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543046">Evaluate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff543208">Execute</a>, and any other method that evaluates an expression.  

After the expression syntax has been changed, the engine sends out notification to the <a href="..\dbgeng\nn-dbgeng-idebugeventcallbacks.md">IDebugEventCallbacks</a> registered with each client.  It also passes the DEBUG_CES_EXPRESSION_SYNTAX flag to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550683">IDebugEventCallbacks::ChangeEngineState</a> method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556697">SetExpressionSyntaxByName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543046">Evaluate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546701">GetExpressionSyntax</a>