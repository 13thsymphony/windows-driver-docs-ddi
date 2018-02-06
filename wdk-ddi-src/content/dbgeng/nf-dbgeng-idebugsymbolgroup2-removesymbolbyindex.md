---
UID: NF:dbgeng.IDebugSymbolGroup2.RemoveSymbolByIndex
title: IDebugSymbolGroup2::RemoveSymbolByIndex method
author: windows-driver-content
description: The RemoveSymbolByIndex method removes the specified symbol from a symbol group.
old-location: debugger\removesymbolbyindex.htm
old-project: debugger
ms.assetid: 1903d454-02d1-4528-9b8f-3c2eab8c6a6a
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSymbolGroup2::RemoveSymbolByIndex, IDebugSymbolGroup2, debugger.removesymbolbyindex, RemoveSymbolByIndex method [Windows Debugging], IDebugSymbolGroup interface, IDebugSymbolGroup::RemoveSymbolByIndex, dbgeng/IDebugSymbolGroup::RemoveSymbolByIndex, ComOther_d532b37e-11c9-4cff-a619-0b9dffef0af1.xml, IDebugSymbolGroup interface [Windows Debugging], RemoveSymbolByIndex method, dbgeng/IDebugSymbolGroup2::RemoveSymbolByIndex, RemoveSymbolByIndex, RemoveSymbolByIndex method [Windows Debugging], IDebugSymbolGroup2 interface, IDebugSymbolGroup2 interface [Windows Debugging], RemoveSymbolByIndex method, RemoveSymbolByIndex method [Windows Debugging]
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
-	IDebugSymbolGroup.RemoveSymbolByIndex
-	IDebugSymbolGroup2.RemoveSymbolByIndex
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# RemoveSymbolByIndex method
The <b>RemoveSymbolByIndex</b> method removes the specified symbol from a symbol group.

## Syntax

````
HRESULT RemoveSymbolByIndex(
  [in] ULONG Index
);
````

## Parameters

`Index`

The index of the symbol to remove. The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.


## Return Value

<b>RemoveSymbolByIndex</b> might return one of the following values:
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

When a symbol is removed, the indexes of the symbols that remain in the symbol group might change.  

For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup.md">IDebugSymbolGroup</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554518">RemoveSymbolByName</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537925">AddSymbol</a>

<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup2.md">IDebugSymbolGroup2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbolGroup::RemoveSymbolByIndex method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>