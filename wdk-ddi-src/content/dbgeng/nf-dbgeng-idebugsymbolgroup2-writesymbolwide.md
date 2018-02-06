---
UID: NF:dbgeng.IDebugSymbolGroup2.WriteSymbolWide
title: IDebugSymbolGroup2::WriteSymbolWide method
author: windows-driver-content
description: The WriteSymbolWide method sets the value of the specified symbol.
old-location: debugger\writesymbolwide.htm
old-project: debugger
ms.assetid: ed77fddf-c23c-4522-a2c4-875f07d249fb
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSymbolGroup2, debugger.writesymbolwide, WriteSymbolWide method [Windows Debugging], IDebugSymbolGroup2 interface [Windows Debugging], WriteSymbolWide method, dbgeng/IDebugSymbolGroup2::WriteSymbolWide, IDebugSymbolGroup2::WriteSymbolWide, WriteSymbolWide, WriteSymbolWide method [Windows Debugging], IDebugSymbolGroup2 interface
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
-	IDebugSymbolGroup2.WriteSymbolWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# WriteSymbolWide method
The <b>WriteSymbolWide</b> method sets the value of the specified symbol.

## Syntax

````
HRESULT WriteSymbolWide(
  [in] ULONG  Index,
  [in] PCWSTR Value
);
````

## Parameters

`Index`

The index of the symbol whose value will be changed. The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.

`Value`

A C++ expression that is evaluated to give the symbol's new value.


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

This method can change symbols only if the symbols are stored in a register or memory location that the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> knowns and if they have not had their type changed to an extension by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553191">OutputAsType</a> method.  

For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup2.md">IDebugSymbolGroup2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549201">GetSymbolValueText</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbolGroup2::WriteSymbolWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>