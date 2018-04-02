---
UID: NF:dbgeng.IDebugRegisters2.GetNumberPseudoRegisters
title: IDebugRegisters2::GetNumberPseudoRegisters method
author: windows-driver-content
description: The GetNumberPseudoRegisters method returns the number of pseudo-registers that are maintained by the debugger engine.
old-location: debugger\getnumberpseudoregisters.htm
old-project: debugger
ms.assetid: 5a71a8e9-323e-4f14-8c97-d6ce4e9bfe65
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetNumberPseudoRegisters method [Windows Debugging], GetNumberPseudoRegisters method [Windows Debugging], IDebugRegisters2 interface, GetNumberPseudoRegisters,IDebugRegisters2.GetNumberPseudoRegisters, IDebugRegisters2, IDebugRegisters2 interface [Windows Debugging], GetNumberPseudoRegisters method, IDebugRegisters2::GetNumberPseudoRegisters, IDebugRegisters_e12950ac-f9b2-4ed2-9ce1-bc3088b65ef1.xml, dbgeng/IDebugRegisters2::GetNumberPseudoRegisters, debugger.getnumberpseudoregisters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: DbgEng.h
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
-	IDebugRegisters2.GetNumberPseudoRegisters
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugRegisters2::GetNumberPseudoRegisters method
The <b>GetNumberPseudoRegisters</b> method returns the number of pseudo-registers that are maintained by the debugger engine.

## Syntax

```
HRESULT GetNumberPseudoRegisters(
  PULONG Number
);
```

## Parameters

`Number`

Receives the number of pseudo-registers that are maintained by the debugger engine.


## Return Value

This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549771">HRESULT Values</a>.

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

Not all of the pseudo-registers are available in all debugging sessions or at all times in a particular session.

The valid indices for pseudo-registers are between zero and the number of pseudo-registers, minus one.

For an overview of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550825">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include DbgEng.h) |