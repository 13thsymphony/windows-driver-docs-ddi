---
UID: NF:dbgeng.IDebugSymbols3.StartSymbolMatchWide
title: IDebugSymbols3::StartSymbolMatchWide method
author: windows-driver-content
description: The StartSymbolMatchWide method initializes a search for symbols whose names match a given pattern.
old-location: debugger\startsymbolmatchwide.htm
old-project: debugger
ms.assetid: dbf8c1a3-cc59-40d7-8355-62891b5b45d2
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], StartSymbolMatchWide method, IDebugSymbols3::StartSymbolMatchWide, StartSymbolMatchWide method [Windows Debugging], StartSymbolMatchWide method [Windows Debugging], IDebugSymbols3 interface, StartSymbolMatchWide,IDebugSymbols3.StartSymbolMatchWide, dbgeng/IDebugSymbols3::StartSymbolMatchWide, debugger.startsymbolmatchwide
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
-	IDebugSymbols3.StartSymbolMatchWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# StartSymbolMatchWide method
The <b>StartSymbolMatchWide</b> method initializes a search for symbols whose names match a given pattern.

## Syntax

````
HRESULT StartSymbolMatchWide(
  [in]  PCWSTR   Pattern,
  [out] PULONG64 Handle
);
````

## Parameters

`Pattern`

Specifies the pattern for which to search.  The search will return all symbols whose names match this pattern.  For details of the syntax of the pattern, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558843">Symbol Syntax and Symbol Matching</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff558819">String Wildcard Syntax</a>.

`Handle`

Receives the handle identifying the search.  This handle can be passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547856">GetNextSymbolMatch</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff543008">EndSymbolMatch</a>.


## Return Value

This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The specified module was not found.

</td>
</tr>
</table>

## Remarks

This method initializes a symbol search.  The results of the search can be obtained by repeated calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547856">GetNextSymbolMatch</a>.  When all the desired results have been found, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff543008">EndSymbolMatch</a> to release resources the engine holds for the search.

For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547856">GetNextSymbolMatch</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543008">EndSymbolMatch</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::StartSymbolMatchWide method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>