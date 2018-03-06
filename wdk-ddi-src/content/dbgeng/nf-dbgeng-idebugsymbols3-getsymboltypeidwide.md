---
UID: NF:dbgeng.IDebugSymbols3.GetSymbolTypeIdWide
title: IDebugSymbols3::GetSymbolTypeIdWide method
author: windows-driver-content
description: The GetSymbolTypeIdWide method returns the type ID and module of the specified symbol.
old-location: debugger\getsymboltypeidwide.htm
old-project: debugger
ms.assetid: b68a5f89-1623-4cab-84bf-3cc6e4031d9b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetSymbolTypeIdWide method [Windows Debugging], GetSymbolTypeIdWide method [Windows Debugging], IDebugSymbols3 interface, GetSymbolTypeIdWide,IDebugSymbols3.GetSymbolTypeIdWide, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetSymbolTypeIdWide method, IDebugSymbols3::GetSymbolTypeIdWide, dbgeng/IDebugSymbols3::GetSymbolTypeIdWide, debugger.getsymboltypeidwide
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
-	IDebugSymbols3.GetSymbolTypeIdWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetSymbolTypeIdWide method
The <b>GetSymbolTypeIdWide</b>  method returns the type ID and module of the specified symbol.

## Syntax

````
HRESULT GetSymbolTypeIdWide(
  [in]            PCWSTR   Symbol,
  [out]           PULONG   TypeId,
  [out, optional] PULONG64 Module
);
````

## Parameters

`Symbol`

Specifies the expression whose type ID is requested.  See the Remarks section for details on the syntax of this expression.

`TypeId`

Receives the type ID.

`Module`

Receives the base address of the module containing the symbol.  For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.  If <i>Module</i> is <b>NULL</b>, this information is not returned.


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
The method was successful

</td>
</tr>
</table>

## Remarks

The <i>Symbol</i> expression may contain structure fields, pointer dereferencing, and array dereferencing -- for example <b>my_struct.some_field[0]</b>.

For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549173">GetSymbolTypeId</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549376">GetTypeId</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetSymbolTypeIdWide method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>