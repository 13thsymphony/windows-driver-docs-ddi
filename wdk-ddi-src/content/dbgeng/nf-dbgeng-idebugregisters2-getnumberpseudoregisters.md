---
UID: NF:dbgeng.IDebugRegisters2.GetNumberPseudoRegisters
title: IDebugRegisters2::GetNumberPseudoRegisters method
author: windows-driver-content
description: The GetNumberPseudoRegisters method returns the number of pseudo-registers that are maintained by the debugger engine.
old-location: debugger\getnumberpseudoregisters.htm
old-project: debugger
ms.assetid: 5a71a8e9-323e-4f14-8c97-d6ce4e9bfe65
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugRegisters2, IDebugRegisters2::GetNumberPseudoRegisters, GetNumberPseudoRegisters
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
req.alt-api: IDebugRegisters2.GetNumberPseudoRegisters
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugRegisters2::GetNumberPseudoRegisters method



## -description
The <b>GetNumberPseudoRegisters</b> method returns the number of pseudo-registers that are maintained by the debugger engine.



## -syntax

````
HRESULT GetNumberPseudoRegisters(
  [out] PULONG Number
);
````


## -parameters

### -param Number [out]

Receives the number of pseudo-registers that are maintained by the debugger engine.


## -returns
This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549771">HRESULT Values</a>.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
Not all of the pseudo-registers are available in all debugging sessions or at all times in a particular session.

The valid indices for pseudo-registers are between zero and the number of pseudo-registers, minus one.

For an overview of the <a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.


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
<dt>Dbgeng.h (include DbgEng.h)</dt>
</dl>
</td>
</tr>
</table>