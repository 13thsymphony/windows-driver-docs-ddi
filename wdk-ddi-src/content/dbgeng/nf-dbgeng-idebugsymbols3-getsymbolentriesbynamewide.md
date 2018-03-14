---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolEntriesByNameWide
title: IDebugSymbols3::GetSymbolEntriesByNameWide method
author: windows-driver-content
description: The GetSymbolEntriesByNameWide method returns the symbols whose names match a given pattern.
old-location: debugger\getsymbolentriesbynamewide.htm
old-project: debugger
ms.assetid: 90f02bfa-58dc-4499-985f-a60336eee341
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetSymbolEntriesByNameWide method [Windows Debugging], GetSymbolEntriesByNameWide method [Windows Debugging], IDebugSymbols3 interface, GetSymbolEntriesByNameWide,IDebugSymbols3.GetSymbolEntriesByNameWide, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetSymbolEntriesByNameWide method, IDebugSymbols3::GetSymbolEntriesByNameWide, dbgeng/IDebugSymbols3::GetSymbolEntriesByNameWide, debugger.getsymbolentriesbynamewide
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
-	dbgeng.h
api_name:
-	IDebugSymbols3.GetSymbolEntriesByNameWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetSymbolEntriesByNameWide method
The <b>GetSymbolEntriesByNameWide</b>  method returns the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">symbols</a> whose names match a given pattern.

## Syntax

````
HRESULT GetSymbolEntriesByNameWide(
  [in]            PCWSTR               Symbol,
  [in]            ULONG                Flags,
  [out, optional] PDEBUG_MODULE_AND_ID Ids,
  [in]            ULONG                IdsCount,
  [out, optional] PULONG               Entries
);
````

## Parameters

`Symbol`

Specifies the pattern used to determine which symbols to return.  This method returns the symbols whose name matches the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558819">string wildcard syntax</a> pattern <i>Symbol</i>.

`Flags`

Set to zero.

`Ids`

Receives the symbols.  This is an array of <i>IdsCount</i> entries of type <a href="..\dbgeng\ns-dbgeng-_debug_module_and_id.md">DEBUG_MODULE_AND_ID</a>.  If <i>Ids</i> is <b>NULL</b>, this information is not returned.

`IdsCount`

Specifies the number of entries that the array <i>Ids</i> can hold.

`Entries`

Receives the number of symbols whose names match the pattern <i>Symbol</i>.  If <i>entries</i> is <b>NULL</b>, this information is not returned.


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

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548476">GetSymbolEntriesByOffset</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetSymbolEntriesByNameWide method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>