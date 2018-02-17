---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolEntryString
title: IDebugSymbols3::GetSymbolEntryString method
author: windows-driver-content
description: The GetSymbolEntryString method returns string information for the specified symbol.
old-location: debugger\getsymbolentrystring.htm
old-project: debugger
ms.assetid: 3ec46b53-f3a8-4fd6-bf94-261ff8accad7
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSymbols3 interface [Windows Debugging], GetSymbolEntryString method, debugger.getsymbolentrystring, IDebugSymbols_cf31d6c1-ffc6-4112-af04-dc023635bb5a.xml, GetSymbolEntryString method [Windows Debugging], IDebugSymbols3 interface, IDebugSymbols3, IDebugSymbols3::GetSymbolEntryString, dbgeng/IDebugSymbols3::GetSymbolEntryString, GetSymbolEntryString method [Windows Debugging], GetSymbolEntryString
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
-	IDebugSymbols3.GetSymbolEntryString
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetSymbolEntryString method
The <b>GetSymbolEntryString</b>  method returns string information for the specified symbol.

## Syntax

````
HRESULT GetSymbolEntryString(
  [in]            PDEBUG_MODULE_AND_ID Id,
  [in]            ULONG                Which,
  [out, optional] PSTR                 Buffer,
  [in]            ULONG                BufferSize,
  [out, optional] PULONG               StringSize
);
````

## Parameters

`Id`

Specifies the symbols whose memory regions are being requested.  The <a href="..\dbgeng\ns-dbgeng-_debug_module_and_id.md">DEBUG_MODULE_AND_ID</a> structure contains the module containing the symbol and the symbol ID of the symbol within the module.

`Which`

Specifies the index of the desired string.  Often this is zero, as most symbols contain just one string (their name).  But some symbols may contain more than one string -- for example, annotation symbols.

`Buffer`

Receives the name of the symbol.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

`BufferSize`

Specifies the size in characters of the buffer <i>Buffer</i>.

`StringSize`

Receives the size in characters of the symbol's name.  If <i>StringSize</i> is <b>NULL</b>, this information is not returned.


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548476">GetSymbolEntriesByOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548458">GetSymbolEntriesByName</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetSymbolEntryString method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>