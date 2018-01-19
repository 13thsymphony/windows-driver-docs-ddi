---
UID : NF:wdbgexts.GetExpressionEx
title : GetExpressionEx function
author : windows-driver-content
description : The GetExpressionEx function evaluates an expression. The expression is evaluated using the MASM evaluator, and can contain aliases.
old-location : debugger\getexpressionex.htm
old-project : debugger
ms.assetid : 07525217-afa5-4fbf-8c84-847ded9556d8
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : GetExpressionEx
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdbgexts.h
req.include-header : Wdbgexts.h, Dbgeng.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : GetExpressionEx
req.alt-loc : wdbgexts.h
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
req.typenames : EXT_TDOP
req.product : Windows 10 or later.
---


# GetExpressionEx function
The <b>GetExpressionEx</b> function evaluates an expression. The expression is evaluated using the MASM evaluator, and can contain aliases.

## Syntax

````
__inline BOOL GetExpressionEx(
   PCSTR   Expression,
   ULONG64 *Value,
   PCSTR   *Remainder
);
````

## Parameters

`Expression`

Specifies the expression to evaluate.  The expression uses the MASM syntax.  For details of this syntax, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552157">MASM Numbers and Operators</a>.

`Value`

Receives the value of the expression.

`Remainder`

Receives a pointer to the first character in the expression <i>Expression</i> that was not used in the evaluation of the expression.


## Return Value

<b>GetExpressionEx</b> returns one of the following values:
<dl>
<dt><b>TRUE</b></dt>
</dl>The expression was evaluated successfully.
<dl>
<dt><b>FALSE</b></dt>
</dl>An error occurred while attempting to evaluate the expression.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdbgexts.h (include Wdbgexts.h, Dbgeng.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wdbgexts\nc-wdbgexts-pwindbg_get_expression.md">GetExpression</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20GetExpressionEx function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>