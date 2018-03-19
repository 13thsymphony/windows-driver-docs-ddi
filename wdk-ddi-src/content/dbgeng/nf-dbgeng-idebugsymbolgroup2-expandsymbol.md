---
UID: NF:dbgeng.IDebugSymbolGroup2.ExpandSymbol
title: IDebugSymbolGroup2::ExpandSymbol method
author: windows-driver-content
description: The ExpandSymbol method adds or removes the children of a symbol from a symbol group.
old-location: debugger\expandsymbol.htm
old-project: debugger
ms.assetid: 314fdeea-10be-4cb3-8bd7-9b1b4b12e534
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: ComOther_894f45d2-9f7b-4d8d-85e3-9240d020ebbe.xml, ExpandSymbol method [Windows Debugging], ExpandSymbol method [Windows Debugging], IDebugSymbolGroup interface, ExpandSymbol method [Windows Debugging], IDebugSymbolGroup2 interface, ExpandSymbol,IDebugSymbolGroup2.ExpandSymbol, IDebugSymbolGroup interface [Windows Debugging], ExpandSymbol method, IDebugSymbolGroup2, IDebugSymbolGroup2 interface [Windows Debugging], ExpandSymbol method, IDebugSymbolGroup2::ExpandSymbol, IDebugSymbolGroup::ExpandSymbol, dbgeng/IDebugSymbolGroup2::ExpandSymbol, dbgeng/IDebugSymbolGroup::ExpandSymbol, debugger.expandsymbol
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
-	IDebugSymbolGroup.ExpandSymbol
-	IDebugSymbolGroup2.ExpandSymbol
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# ExpandSymbol method
The <b>ExpandSymbol</b> method adds or removes the children of a symbol from a symbol group.

## Syntax

````
HRESULT ExpandSymbol(
  [in] ULONG Index,
  [in] BOOL  Expand
);
````

## Parameters

`Index`

The index of the symbol whose children will be added or removed.  The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.

`Expand`

A Boolean value that specifies whether to add or remove the symbols children from the symbol group.  If <i>Expand</i> is true, the children are added.  If <i>Expand</i> is false, the children are removed.


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
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The symbol has no children to add.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The depth of the symbol is DEBUG_SYMBOL_EXPANSION_LEVEL_MASK,  which is the maximum depth. This depth prevented the specified symbol's children from being added to this symbol group.

</td>
</tr>
</table>
 

This method can also return other error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.

## Remarks

For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup.md">IDebugSymbolGroup</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup2.md">IDebugSymbolGroup2</a>