---
UID: NF:dbgeng.IDebugControl3.SetExpressionSyntax
title: IDebugControl3::SetExpressionSyntax method
author: windows-driver-content
description: The SetExpressionSyntax method sets the syntax that the engine will use to evaluate expressions.
old-location: debugger\setexpressionsyntax.htm
old-project: debugger
ms.assetid: ab98312f-0240-498f-992a-b05cbcc64c04
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl3, IDebugControl3::SetExpressionSyntax, SetExpressionSyntax
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
req.alt-api: IDebugControl3.SetExpressionSyntax
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
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::SetExpressionSyntax method



## -description
The <b>SetExpressionSyntax</b> method sets the syntax that the engine will use to evaluate expressions.



## -syntax

````
HRESULT SetExpressionSyntax(
  [in] ULONG Flags
);
````


## -parameters

### -param Flags [in]

Specifies the syntax that the engine will use to evaluate expressions.  It can be one of the following values:




### -param DEBUG_EXPR_MASM

Expressions will be evaluated according to MASM syntax. For details of this syntax, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552157">MASM Numbers and Operators</a>.


### -param DEBUG_EXPR_CPLUSPLUS

Expressions will be evaluated according to C++ syntax. For details of this syntax, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540372">C++ Numbers and Operators</a>.

</dd>
</dl>

## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
The expression syntax is a global setting within the engine, so setting the expression syntax will affect all clients.

The expression syntax of the engine determines how the engine will interpret expressions passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543046">Evaluate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff543208">Execute</a>, and any other method that evaluates an expression.  

After the expression syntax has been changed, the engine sends out notification to the <a href="..\dbgeng\nn-dbgeng-idebugeventcallbacks.md">IDebugEventCallbacks</a> registered with each client.  It also passes the DEBUG_CES_EXPRESSION_SYNTAX flag to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550683">IDebugEventCallbacks::ChangeEngineState</a> method.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546701">GetExpressionSyntax</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556697">SetExpressionSyntaxByName</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543046">Evaluate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl3::SetExpressionSyntax method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

