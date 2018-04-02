---
UID: NF:dbgeng.IDebugSymbols3.ReloadWide
title: IDebugSymbols3::ReloadWide method
author: windows-driver-content
description: The ReloadWide method deletes the engine's symbol information for the specified module and reload these symbols as needed.
old-location: debugger\reloadwide.htm
old-project: debugger
ms.assetid: 3975bc55-15e3-45ca-82df-76c5ed3b0086
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], ReloadWide method, IDebugSymbols3::ReloadWide, ReloadWide method [Windows Debugging], ReloadWide method [Windows Debugging], IDebugSymbols3 interface, ReloadWide,IDebugSymbols3.ReloadWide, dbgeng/IDebugSymbols3::ReloadWide, debugger.reloadwide
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
-	IDebugSymbols3.ReloadWide
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugSymbols3::ReloadWide method
The <b>ReloadWide</b>  method deletes the engine's symbol information for the specified module and reload these symbols as needed.

## Syntax

```
HRESULT ReloadWide(
  PCWSTR Module
);
```

## Parameters

`Module`

Specifies the module to reload.


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
The method was successful

</td>
</tr>
</table>
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

## Remarks

This method behaves the same way as the debugger command <b>.reload</b>.  The <i>Module</i> parameter is treated the same way as the arguments to <b>.reload</b>.  For example, setting the <i>Module</i> parameter to "/u ntdll.dll" has the same effect as the command <b>.reload /u ntdll.dll</b>.

For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564805">.reload (Reload Module)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>