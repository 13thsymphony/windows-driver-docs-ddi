---
UID: NF:dbgeng.IDebugSymbolGroup2.GetSymbolOffset
title: IDebugSymbolGroup2::GetSymbolOffset method
author: windows-driver-content
description: The GetSymbolOffset method retrieves the location in the process's virtual address space of a symbol in a symbol group, if the symbol has an absolute address.
old-location: debugger\getsymboloffset.htm
old-project: debugger
ms.assetid: da3ddebc-109e-43fb-a0e9-fd89d90dbbc7
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetSymbolOffset method [Windows Debugging], IDebugSymbolGroup2 interface, IDebugSymbolGroup2::GetSymbolOffset, IDebugSymbolGroup2, dbgeng/IDebugSymbolGroup2::GetSymbolOffset, ComOther_11a91301-541c-4bc3-aa1e-614db8170e03.xml, GetSymbolOffset, debugger.getsymboloffset, IDebugSymbolGroup2 interface [Windows Debugging], GetSymbolOffset method, GetSymbolOffset method [Windows Debugging]
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
-	IDebugSymbolGroup2.GetSymbolOffset
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetSymbolOffset method
The <b>GetSymbolOffset</b> method retrieves the location in the process's virtual address space of a symbol in a symbol group, if the symbol has an absolute address.

## Syntax

````
HRESULT GetSymbolOffset(
  [in]  ULONG    Index,
  [out] PULONG64 Offset
);
````

## Parameters

`Index`

The index of the symbol whose address you want.  The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.

`Offset`

The location in the process's virtual address space of the symbol.


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
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The symbol does not have an absolute address.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>

<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup2.md">IDebugSymbolGroup2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbolGroup2::GetSymbolOffset method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>