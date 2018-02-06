---
UID: NF:dbgeng.IDebugControl4.GetExpressionSyntaxNamesWide
title: IDebugControl4::GetExpressionSyntaxNamesWide method
author: windows-driver-content
description: The GetExpressionSyntaxNamesWide method returns the full and abbreviated names of an expression syntax.
old-location: debugger\getexpressionsyntaxnameswide.htm
old-project: debugger
ms.assetid: 4d381718-366b-483b-804d-b12b31832b35
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugControl4 interface [Windows Debugging], GetExpressionSyntaxNamesWide method, IDebugControl4, GetExpressionSyntaxNamesWide method [Windows Debugging], IDebugControl4 interface, GetExpressionSyntaxNamesWide, IDebugControl4::GetExpressionSyntaxNamesWide, GetExpressionSyntaxNamesWide method [Windows Debugging], dbgeng/IDebugControl4::GetExpressionSyntaxNamesWide, debugger.getexpressionsyntaxnameswide
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
-	IDebugControl4.GetExpressionSyntaxNamesWide
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetExpressionSyntaxNamesWide method
The <b>GetExpressionSyntaxNamesWide</b> method returns the full and abbreviated names of an expression syntax.

## Syntax

````
HRESULT GetExpressionSyntaxNamesWide(
  [in]            ULONG  Index,
  [out, optional] PWSTR  FullNameBuffer,
  [in]            ULONG  FullNameBufferSize,
  [out, optional] PULONG FullNameSize,
  [out, optional] PWSTR  AbbrevNameBuffer,
  [in]            ULONG  AbbrevNameBufferSize,
  [out, optional] PULONG AbbrevNameSize
);
````

## Parameters

`Index`

Specifies the index of the expression syntax.  <i>Index</i> should be between zero and the number of expression syntaxes returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff547913">GetNumberExpressionSyntaxes</a> minus one.

`FullNameBuffer`

Receives the full name of the expression syntax.  If <i>FullNameBuffer</i> is <b>NULL</b>, this information is not returned.

`FullNameBufferSize`

Specifies the size, in characters, of the buffer <i>FullNameBuffer</i>.

`FullNameSize`

Receives the size, in characters, of the full name of the expression syntax.  If <i>FullNameSize</i> is <b>NULL</b>, this information is not returned.

`AbbrevNameBuffer`

Receives the abbreviated name of the expression syntax.  If <i>AbbrevNameBuffer</i> is <b>NULL</b>, this information is not returned.

`AbbrevNameBufferSize`

Specifies the size, in characters, of the buffer <i>AbbrevNameBufferSize</i>.

`AbbrevNameSize`

Receives the size, in characters, of the abbreviated name of the expression syntax.  If <i>AbbrevNameSize</i> is <b>NULL</b>, this information is not returned.


## Return Value

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
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
The method was successful.  However, either <i>FullNameBufferSize</i> or <i>AbbrevNameBufferSize</i> was smaller than the size of the respective expression syntax name, and the name was truncated to fit inside the buffer.

</td>
</tr>
</table>

## Remarks

Currently, there are two expression syntaxes, their full names are "Microsoft Assembler expressions" and "C++ source expressions."  The corresponding abbreviated expression syntaxes are "MASM" and "C++."

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556697">SetExpressionSyntaxByName</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547913">GetNumberExpressionSyntaxes</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543046">Evaluate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::GetExpressionSyntaxNamesWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>