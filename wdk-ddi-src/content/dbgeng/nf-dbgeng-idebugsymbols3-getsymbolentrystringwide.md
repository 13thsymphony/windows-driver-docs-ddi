---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolEntryStringWide
title: IDebugSymbols3::GetSymbolEntryStringWide method
author: windows-driver-content
description: The GetSymbolEntryStringWide method returns string information for the specified symbol.
old-location: debugger\getsymbolentrystringwide.htm
old-project: debugger
ms.assetid: 65a8d959-98f5-4545-8865-d6d81a752d48
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetSymbolEntryStringWide method [Windows Debugging], GetSymbolEntryStringWide method [Windows Debugging], IDebugSymbols3 interface, GetSymbolEntryStringWide,IDebugSymbols3.GetSymbolEntryStringWide, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetSymbolEntryStringWide method, IDebugSymbols3::GetSymbolEntryStringWide, dbgeng/IDebugSymbols3::GetSymbolEntryStringWide, debugger.getsymbolentrystringwide
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
-	IDebugSymbols3.GetSymbolEntryStringWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugSymbols3::GetSymbolEntryStringWide method
The <b>GetSymbolEntryStringWide</b>  method returns string information for the specified symbol.

## Syntax

```
HRESULT GetSymbolEntryStringWide(
  PDEBUG_MODULE_AND_ID Id,
  ULONG                Which,
  PWSTR                Buffer,
  ULONG                BufferSize,
  PULONG               StringSize
);
```

## Parameters

`Id`

Specifies the symbols whose memory regions are being requested.  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff541511">DEBUG_MODULE_AND_ID</a> structure contains the module containing the symbol and the symbol ID of the symbol within the module.

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

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548458">GetSymbolEntriesByName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548476">GetSymbolEntriesByOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>