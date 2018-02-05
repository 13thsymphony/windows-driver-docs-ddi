---
UID : NF:dbgeng.IDebugSymbolGroup2.GetSymbolTypeName
title : IDebugSymbolGroup2::GetSymbolTypeName method
author : windows-driver-content
description : The GetSymbolTypeName methods return the name of the specified symbol's type.
old-location : debugger\getsymboltypename.htm
old-project : debugger
ms.assetid : e15b418e-bf4a-49c0-bdb3-24973513e654
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : GetSymbolTypeName method [Windows Debugging], IDebugSymbolGroup2, IDebugSymbolGroup2 interface [Windows Debugging], GetSymbolTypeName method, GetSymbolTypeName method [Windows Debugging], IDebugSymbolGroup2 interface, dbgeng/IDebugSymbolGroup2::GetSymbolTypeName, debugger.getsymboltypename, ComOther_27d4a23e-4566-4b37-a692-2b82310ae8e9.xml, GetSymbolTypeName, IDebugSymbolGroup2::GetSymbolTypeName
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
req.typenames : DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetSymbolTypeName method
The <b>GetSymbolTypeName</b>  methods return the name of the specified symbol's type.

## Syntax

````
HRESULT GetSymbolTypeName(
  [in]            ULONG  Index,
  [out, optional] PSTR   Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG NameSize
);
````

## Parameters

`Index`

The index of the symbol whose type name you want. The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.

`Buffer`

The name of the symbol's type.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

`BufferSize`

The size, in characters, of the <i>Buffer</i> buffer.

`NameSize`

The size, in characters, of the name of the symbol's type.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.


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
The size of the buffer was smaller than the size of the name of the symbol's type. The buffer is filled with the truncated name.

</td>
</tr>
</table> 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.

## Remarks

For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup2.md">IDebugSymbolGroup2</a>

<a href="https://msdn.microsoft.com/09aa3ba9-d5b6-4c08-93f1-f7beca9350a1">IDebugSymbols::GetTypeName</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbolGroup2::GetSymbolTypeName method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>