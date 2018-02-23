---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolModule
title: IDebugSymbols3::GetSymbolModule method
author: windows-driver-content
description: The GetSymbolModule method returns the base address of module which contains the specified symbol.
old-location: debugger\getsymbolmodule.htm
old-project: Debugger
ms.assetid: f3774204-86c3-467b-96ba-739f19d300e3
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugSymbols2::GetSymbolModule, GetSymbolModule method [Windows Debugging], IDebugSymbols3 interface, debugger.getsymbolmodule, GetSymbolModule method [Windows Debugging], GetSymbolModule method [Windows Debugging], IDebugSymbols interface, GetSymbolModule, IDebugSymbols3 interface [Windows Debugging], GetSymbolModule method, IDebugSymbols2 interface [Windows Debugging], GetSymbolModule method, GetSymbolModule method [Windows Debugging], IDebugSymbols2 interface, IDebugSymbols, dbgeng/IDebugSymbols2::GetSymbolModule, IDebugSymbols2, IDebugSymbols3, IDebugSymbols::GetSymbolModule, IDebugSymbols3::GetSymbolModule, dbgeng/IDebugSymbols::GetSymbolModule, IDebugSymbols_a680615c-bc2a-4fa3-a83a-6960ed64c1e9.xml, dbgeng/IDebugSymbols3::GetSymbolModule, IDebugSymbols interface [Windows Debugging], GetSymbolModule method
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
-	IDebugSymbols.GetSymbolModule
-	IDebugSymbols2.GetSymbolModule
-	IDebugSymbols3.GetSymbolModule
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetSymbolModule method
The <b>GetSymbolModule</b> method returns the base address of module which contains the specified symbol.

## Syntax

````
HRESULT GetSymbolModule(
  [in]  PCSTR    Symbol,
  [out] PULONG64 Base
);
````

## Parameters

`Symbol`

Specifies the name of the symbol to look up.  See the Remarks section for details of the syntax of this name.

`Base`

Receives the location in the target's memory address space of the base of the module.  For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.


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
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The symbol or module could not be found.

</td>
</tr>
</table>

## Remarks

The string <i>Symbol</i> must contain an exclamation point ( <b>!</b> ).  If <i>Symbol</i> is a module-qualified symbol name (for example, <b>mymodules!main</b>) or if the module name is omitted (for example, <b>!main</b>), the engine will search for this symbol and return the module in which it is found.  If <i>Symbol</i> contains just a module name (for example, <b>mymodule!</b>) the engine returns the first module with this module name.

For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |