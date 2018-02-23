---
UID: NF:dbgeng.IDebugSymbolGroup.GetNumberSymbols
title: IDebugSymbolGroup::GetNumberSymbols method
author: windows-driver-content
description: The GetNumberSymbols method returns the number of symbols that are contained in a symbol group.
old-location: debugger\getnumbersymbols.htm
old-project: Debugger
ms.assetid: 5a202530-7146-472d-9560-580871cd56ec
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugSymbolGroup, GetNumberSymbols method [Windows Debugging], IDebugSymbolGroup interface, IDebugSymbolGroup2 interface [Windows Debugging], GetNumberSymbols method, IDebugSymbolGroup interface [Windows Debugging], GetNumberSymbols method, GetNumberSymbols method [Windows Debugging], IDebugSymbolGroup::GetNumberSymbols, dbgeng/IDebugSymbolGroup::GetNumberSymbols, GetNumberSymbols, dbgeng/IDebugSymbolGroup2::GetNumberSymbols, debugger.getnumbersymbols, GetNumberSymbols method [Windows Debugging], IDebugSymbolGroup2 interface, IDebugSymbolGroup2::GetNumberSymbols, ComOther_e355317f-ba58-4d2a-a8f7-ad3cf4b17607.xml
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
-	IDebugSymbolGroup.GetNumberSymbols
-	IDebugSymbolGroup2.GetNumberSymbols
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetNumberSymbols method
The <b>GetNumberSymbols</b> method returns the number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">symbols</a> that are contained in a symbol group.

## Syntax

````
HRESULT GetNumberSymbols(
  [out] PULONG Number
);
````

## Parameters

`Number`

The number of symbols that are contained in this symbol group.


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

Each symbol in a symbol group is identified by an <i>index</i>.  This index is a number between zero and the number that is returned to <i>Number</i> minus one.  Every time that a symbol is added or removed from the symbol group, the index of all of the symbols in the group might change.

For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |