---
UID : NF:dbgeng.IDebugSymbols3.GetSymbolModuleWide
title : IDebugSymbols3::GetSymbolModuleWide method
author : windows-driver-content
description : The GetSymbolModuleWide method returns the base address of module which contains the specified symbol.
old-location : debugger\getsymbolmodulewide.htm
old-project : debugger
ms.assetid : 4c1284da-b086-46f3-aeea-0afe6a2f1031
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : dbgeng/IDebugSymbols3::GetSymbolModuleWide, GetSymbolModuleWide method [Windows Debugging], IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging], GetSymbolModuleWide method, IDebugSymbols3::GetSymbolModuleWide, IDebugSymbols3, debugger.getsymbolmodulewide, GetSymbolModuleWide method [Windows Debugging], GetSymbolModuleWide
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
req.typenames : "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetSymbolModuleWide method
The <b>GetSymbolModuleWide</b> method returns the base address of module which contains the specified symbol.

## Syntax

````
HRESULT GetSymbolModuleWide(
  [in]  PCWSTR   Symbol,
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
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |