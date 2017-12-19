---
UID: NF.dbgeng.IDebugSymbols3.GetSymbolEntriesByNameWide
title: IDebugSymbols3::GetSymbolEntriesByNameWide method
author: windows-driver-content
description: The GetSymbolEntriesByNameWide method returns the symbols whose names match a given pattern.
old-location: debugger\getsymbolentriesbynamewide.htm
old-project: Debugger
ms.assetid: 90f02bfa-58dc-4499-985f-a60336eee341
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IDebugSymbols3, IDebugSymbols3::GetSymbolEntriesByNameWide, GetSymbolEntriesByNameWide
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
req.alt-api: IDebugSymbols3.GetSymbolEntriesByNameWide
req.alt-loc: dbgeng.h
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
---

# IDebugSymbols3::GetSymbolEntriesByNameWide method



## -description
The <b>GetSymbolEntriesByNameWide</b>  method returns the <a href="debugger.symbols#symbols#symbols">symbols</a> whose names match a given pattern.



## -syntax

````
HRESULT GetSymbolEntriesByNameWide(
  [in]            PCWSTR               Symbol,
  [in]            ULONG                Flags,
  [out, optional] PDEBUG_MODULE_AND_ID Ids,
  [in]            ULONG                IdsCount,
  [out, optional] PULONG               Entries
);
````


## -parameters

### -param Symbol [in]

Specifies the pattern used to determine which symbols to return.  This method returns the symbols whose name matches the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558819">string wildcard syntax</a> pattern <i>Symbol</i>.


### -param Flags [in]

Set to zero.


### -param Ids [out, optional]

Receives the symbols.  This is an array of <i>IdsCount</i> entries of type <a href="debugger.debug_module_and_id">DEBUG_MODULE_AND_ID</a>.  If <i>Ids</i> is <b>NULL</b>, this information is not returned.


### -param IdsCount [in]

Specifies the number of entries that the array <i>Ids</i> can hold.


### -param Entries [out, optional]

Receives the number of symbols whose names match the pattern <i>Symbol</i>.  If <i>entries</i> is <b>NULL</b>, this information is not returned.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>
</dt>
<dt>
<a href="debugger.getsymbolentriesbyoffset">GetSymbolEntriesByOffset</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugSymbols3::GetSymbolEntriesByNameWide method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

