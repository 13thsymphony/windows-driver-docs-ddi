---
UID: NF:dbgeng.IDebugSymbols2.CreateSymbolGroup
title: IDebugSymbols2::CreateSymbolGroup method
author: windows-driver-content
description: The CreateSymbolGroup method creates a new symbol group.
old-location: debugger\createsymbolgroup.htm
old-project: debugger
ms.assetid: f55aa290-5e57-48d8-9454-370c494bbd65
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: CreateSymbolGroup method [Windows Debugging], CreateSymbolGroup method [Windows Debugging], IDebugSymbols interface, CreateSymbolGroup method [Windows Debugging], IDebugSymbols2 interface, CreateSymbolGroup method [Windows Debugging], IDebugSymbols3 interface, CreateSymbolGroup,IDebugSymbols2.CreateSymbolGroup, IDebugSymbols interface [Windows Debugging], CreateSymbolGroup method, IDebugSymbols2, IDebugSymbols2 interface [Windows Debugging], CreateSymbolGroup method, IDebugSymbols2::CreateSymbolGroup, IDebugSymbols3 interface [Windows Debugging], CreateSymbolGroup method, IDebugSymbols3::CreateSymbolGroup, IDebugSymbols::CreateSymbolGroup, IDebugSymbols_fe8b31b2-0c5c-4dde-9d60-a353893e3f65.xml, dbgeng/IDebugSymbols2::CreateSymbolGroup, dbgeng/IDebugSymbols3::CreateSymbolGroup, dbgeng/IDebugSymbols::CreateSymbolGroup, debugger.createsymbolgroup
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
-	Dbgeng.h
api_name:
-	IDebugSymbols.CreateSymbolGroup
-	IDebugSymbols2.CreateSymbolGroup
-	IDebugSymbols3.CreateSymbolGroup
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# CreateSymbolGroup method
The <b>CreateSymbolGroup</b>  method creates a new symbol group.

## Syntax

````
HRESULT CreateSymbolGroup(
  [out] IDebugSymbolGroup **Group
);
````

## Parameters

`Group`

Receives an interface pointer for the new <a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup.md">IDebugSymbolGroup</a> object.


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
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

## Remarks

The newly created symbol group is empty; it does not contain any <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">symbols</a>.  Symbols may be added to the symbol group using <a href="https://msdn.microsoft.com/b77de459-b5ac-4752-89eb-f24fdde36134">IDebugSymbolGroup::AddSymbol</a>.

References to the returned object are managed like other COM objects, using the <b>IUnknown::AddRef</b> and <b>IUnknown::Release</b> methods.  In particular, the <b>IUnknown::Release</b> method must be called when the returned object is no longer needed.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff560088">Using Client Objects</a> for more information about using COM interfaces in the Debugger Engine API.

For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/b77de459-b5ac-4752-89eb-f24fdde36134">IDebugSymbolGroup::AddSymbol</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup.md">IDebugSymbolGroup</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>