---
UID: NF:dbgeng.IDebugSymbols3.AddSyntheticSymbolWide
title: IDebugSymbols3::AddSyntheticSymbolWide method
author: windows-driver-content
description: The AddSyntheticSymbolWide method adds a synthetic symbol to a module in the current process.
old-location: debugger\addsyntheticsymbolwide.htm
old-project: debugger
ms.assetid: 06d4d1f1-8d28-46cc-8c80-8a67cf4ae4c3
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: AddSyntheticSymbolWide method [Windows Debugging], AddSyntheticSymbolWide method [Windows Debugging], IDebugSymbols3 interface, AddSyntheticSymbolWide,IDebugSymbols3.AddSyntheticSymbolWide, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], AddSyntheticSymbolWide method, IDebugSymbols3::AddSyntheticSymbolWide, dbgeng/IDebugSymbols3::AddSyntheticSymbolWide, debugger.addsyntheticsymbolwide
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
-	Dbgeng.h
api_name:
-	IDebugSymbols3.AddSyntheticSymbolWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugSymbols3::AddSyntheticSymbolWide method
The <b>AddSyntheticSymbolWide</b>  method adds a synthetic symbol to a module in the <a href="https://msdn.microsoft.com/295b05a3-e27f-4761-a562-7e87e25bfd3b">current process</a>.

## Syntax

```
HRESULT AddSyntheticSymbolWide(
  ULONG64              Offset,
  ULONG                Size,
  PCWSTR               Name,
  ULONG                Flags,
  PDEBUG_MODULE_AND_ID Id
);
```

## Parameters

`Offset`

Specifies the location in the process's virtual address space of the synthetic symbol.

`Size`

Specifies the size in bytes of the synthetic symbol.

`Name`

Specifies the name of the synthetic symbol.

`Flags`

Set to DEBUG_ADDSYNTHSYM_DEFAULT.

`Id`

Receives the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541511">DEBUG_MODULE_AND_ID</a> structure that identifies the synthetic symbol.  If <i>Id</i> is <b>NULL</b>, this information is not returned.


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
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

## Remarks

The location of the synthetic symbol must not be the same as the location of another symbol.

If the module containing a synthetic symbol is reloaded - for example, by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554379">Reload</a> with the <i>Module</i> parameter set to the name of the module - the synthetic symbol will be discarded.

For more information about synthetic symbols, see <a href="https://msdn.microsoft.com/1de1441f-b4d7-49e9-87ad-392a75b3d4be">Synthetic Symbols</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537937">AddSyntheticModule</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554542">RemoveSyntheticSymbol</a>