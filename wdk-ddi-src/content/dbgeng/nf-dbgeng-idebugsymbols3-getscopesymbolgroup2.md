---
UID: NF:dbgeng.IDebugSymbols3.GetScopeSymbolGroup2
title: IDebugSymbols3::GetScopeSymbolGroup2 method
author: windows-driver-content
description: The GetScopeSymbolGroup2 method returns a symbol group containing the symbols in the current target's scope.
old-location: debugger\getscopesymbolgroup2.htm
old-project: debugger
ms.assetid: 2bc0cd81-db9b-4646-838b-0e66c0667202
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetScopeSymbolGroup2 method [Windows Debugging], debugger.getscopesymbolgroup2, IDebugSymbols3 interface [Windows Debugging], GetScopeSymbolGroup2 method, dbgeng/IDebugSymbols3::GetScopeSymbolGroup2, GetScopeSymbolGroup2, GetScopeSymbolGroup2 method [Windows Debugging], IDebugSymbols3 interface, IDebugSymbols3::GetScopeSymbolGroup2, IDebugSymbols3
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
-	IDebugSymbols3.GetScopeSymbolGroup2
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetScopeSymbolGroup2 method
The <b>GetScopeSymbolGroup2</b>  method returns a symbol group containing the symbols in the current target's scope.

## Syntax

````
HRESULT GetScopeSymbolGroup2(
  [in]           ULONG                Flags,
  [in, optional] PDEBUG_SYMBOL_GROUP2 Update,
  [out]          PDEBUG_SYMBOL_GROUP2 *Symbols
);
````

## Parameters

`Flags`

Specifies a bit-set used to determine which symbols to include in the symbol group.  To include all symbols, set <i>Flags</i> to DEBUG_SCOPE_GROUP_ALL.  The following bit-flags determine which symbols are included.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_SCOPE_GROUP_ARGUMENTS

</td>
<td>
Include the function arguments for the current scope.

</td>
</tr>
<tr>
<td>
DEBUG_SCOPE_GROUP_LOCALS

</td>
<td>
Include the local variables for the current scope.

</td>
</tr>
</table>

`Update`

Specifies a previously created symbol group that will be updated to reflect the current scope.  If <i>Update</i> is <b>NULL</b>, a new symbol group interface object is created.

`Symbols`

Receives the symbol group interface object for the current scope.  For details on this interface, see <a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup.md">IDebugSymbolGroup</a>


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
</table>

## Remarks

The <i>Update</i> parameter allows for efficient updates when stepping through code. Instead of creating and populating a new symbol group, the old symbol group can be updated.

For more information about scopes and symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup.md">IDebugSymbolGroup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548270">GetScope</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetScopeSymbolGroup2 method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>