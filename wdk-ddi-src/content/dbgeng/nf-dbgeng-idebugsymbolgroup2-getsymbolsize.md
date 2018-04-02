---
UID: NF:dbgeng.IDebugSymbolGroup2.GetSymbolSize
title: IDebugSymbolGroup2::GetSymbolSize method
author: windows-driver-content
description: The GetSymbolSize method returns the size of a symbol's value.
old-location: debugger\getsymbolsize.htm
old-project: debugger
ms.assetid: f35bbbeb-585b-47b0-ae36-bd37fe9e1bbc
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: ComOther_a6e69468-38f9-449d-9bd7-0ef52585f2aa.xml, GetSymbolSize method [Windows Debugging], GetSymbolSize method [Windows Debugging], IDebugSymbolGroup2 interface, GetSymbolSize,IDebugSymbolGroup2.GetSymbolSize, IDebugSymbolGroup2, IDebugSymbolGroup2 interface [Windows Debugging], GetSymbolSize method, IDebugSymbolGroup2::GetSymbolSize, dbgeng/IDebugSymbolGroup2::GetSymbolSize, debugger.getsymbolsize
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
-	IDebugSymbolGroup2.GetSymbolSize
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugSymbolGroup2::GetSymbolSize method
The <b>GetSymbolSize</b> method returns the size of a symbol's value.

## Syntax

```
HRESULT GetSymbolSize(
  ULONG  Index,
  PULONG Size
);
```

## Parameters

`Index`

The index of the symbol to remove. The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.

`Size`

The size, in bytes, of the symbol's value. This information might not be available. If this information is not available, <i>Size</i> is set to zero.  For some symbols (for example, a function's code), the data might be split over multiple regions. In this situation, <i>Size</i> is not meaningful.


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
The symbol does not have type data associated with it.

</td>
</tr>
</table>
 

This method can also return other error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.

## Remarks

For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550846">IDebugSymbolGroup2</a>



<a href="https://msdn.microsoft.com/b6f03eb5-e386-4e88-a729-db08f1fa460c">IDebugSymbols::GetTypeSize</a>