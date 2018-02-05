---
UID : NF:dbgeng.IDebugSymbols3.GetSymbolEntriesByOffset
title : IDebugSymbols3::GetSymbolEntriesByOffset method
author : windows-driver-content
description : The GetSymbolEntriesByOffset method returns the symbols which are located at a specified address.
old-location : debugger\getsymbolentriesbyoffset.htm
old-project : debugger
ms.assetid : 93df59dc-adae-49b7-acf4-1cfdd142fd96
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : debugger.getsymbolentriesbyoffset, IDebugSymbols3::GetSymbolEntriesByOffset, GetSymbolEntriesByOffset method [Windows Debugging], IDebugSymbols_dba4bc10-a8a8-476d-b668-652c24743ea5.xml, GetSymbolEntriesByOffset method [Windows Debugging], IDebugSymbols3 interface, dbgeng/IDebugSymbols3::GetSymbolEntriesByOffset, GetSymbolEntriesByOffset, IDebugSymbols3 interface [Windows Debugging], GetSymbolEntriesByOffset method, IDebugSymbols3
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


# GetSymbolEntriesByOffset method
The <b>GetSymbolEntriesByOffset</b> method returns the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">symbols</a> which are located at a specified address.

## Syntax

````
HRESULT GetSymbolEntriesByOffset(
  [in]            ULONG64              Offset,
  [in]            ULONG                Flags,
  [out, optional] PDEBUG_MODULE_AND_ID Ids,
  [out, optional] PULONG64             Displacements,
  [in]            ULONG                IdsCount,
  [out, optional] PULONG               Entries
);
````

## Parameters

`Offset`

Specifies a location in the process's memory address space within the desired symbol's range.  Not all symbols have a known range, so, for best results, use the base address of the symbol.

`Flags`

Set to zero.

`Ids`

Receives the symbols.  This is an array of <i>IdsCount</i> entries of type <a href="..\dbgeng\ns-dbgeng-_debug_module_and_id.md">DEBUG_MODULE_AND_ID</a>.  If <i>Ids</i> is <b>NULL</b>, this information is not returned.

`Displacements`

Receives the differences between the base addresses of the found symbols and the given address according to the symbol's range.

`IdsCount`

Specifies the number of entries that the arrays <i>Ids</i> and <i>Displacements</i> can hold.

`Entries`

Receives the number of symbols located at <i>Offset</i>.  If <i>Entries</i> is <b>NULL</b>, this information is not returned.


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

For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548458">GetSymbolEntriesByName</a>

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetSymbolEntriesByOffset method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>