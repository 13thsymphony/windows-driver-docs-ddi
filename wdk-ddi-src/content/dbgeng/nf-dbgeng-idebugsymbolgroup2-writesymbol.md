---
UID: NF:dbgeng.IDebugSymbolGroup2.WriteSymbol
title: IDebugSymbolGroup2::WriteSymbol method
author: windows-driver-content
description: The WriteSymbol methods set the value of the specified symbol.
old-location: debugger\writesymbol.htm
old-project: debugger
ms.assetid: c0c23778-767a-4304-9ecf-c76337261e27
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ComOther_3b8938be-b82e-404c-b80f-36e1ceedc353.xml, IDebugSymbolGroup interface [Windows Debugging], WriteSymbol method, IDebugSymbolGroup2, IDebugSymbolGroup2 interface [Windows Debugging], WriteSymbol method, IDebugSymbolGroup2::WriteSymbol, IDebugSymbolGroup::WriteSymbol, WriteSymbol method [Windows Debugging], WriteSymbol method [Windows Debugging], IDebugSymbolGroup interface, WriteSymbol method [Windows Debugging], IDebugSymbolGroup2 interface, WriteSymbol,IDebugSymbolGroup2.WriteSymbol, dbgeng/IDebugSymbolGroup2::WriteSymbol, dbgeng/IDebugSymbolGroup::WriteSymbol, debugger.writesymbol
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugSymbolGroup.WriteSymbol
-	IDebugSymbolGroup2.WriteSymbol
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# WriteSymbol method
The <b>WriteSymbol</b>  methods set the value of the specified symbol.

## Syntax

````
HRESULT WriteSymbol(
  [in] ULONG Index,
  [in] PCSTR Value
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

The <b>WriteSymbol</b>  method can change symbols only if the symbols are stored in a register or memory location that the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> knowns and if they have not had their type changed to an extension by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553191">OutputAsType</a> method.  

For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup2.md">IDebugSymbolGroup2</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup.md">IDebugSymbolGroup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549201">GetSymbolValueText</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbolGroup::WriteSymbol method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>