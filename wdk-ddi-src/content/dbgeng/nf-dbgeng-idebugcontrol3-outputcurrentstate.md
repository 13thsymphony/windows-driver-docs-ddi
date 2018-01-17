---
UID: NF:dbgeng.IDebugControl3.OutputCurrentState
title: IDebugControl3::OutputCurrentState method
author: windows-driver-content
description: The OutputCurrentState method prints the current state of the current target to the debugger console.
old-location: debugger\outputcurrentstate.htm
old-project: debugger
ms.assetid: 3d176438-5551-48a4-b757-81c14d84c075
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl3, IDebugControl3::OutputCurrentState, OutputCurrentState
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
req.alt-api: IDebugControl.OutputCurrentState,IDebugControl2.OutputCurrentState,IDebugControl3.OutputCurrentState
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
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::OutputCurrentState method



## -description
The <b>OutputCurrentState</b> method prints the current state of the current target to the debugger console.



## -syntax

````
HRESULT OutputCurrentState(
  [in] ULONG OutputControl,
  [in] ULONG Flags
);
````


## -parameters

### -param OutputControl [in]

Specifies which clients to send the output to.  For possible values see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a>.


### -param Flags [in]

Specifies the bit set that determines the information to print to the debugger console.  <i>Flags</i> can be any combination of values from the following table.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_CURRENT_SYMBOL

</td>
<td>
Symbol string for the address of the current instruction.

</td>
</tr>
<tr>
<td>
DEBUG_CURRENT_DISASM

</td>
<td>
Disassembly of the current instruction.

</td>
</tr>
<tr>
<td>
DEBUG_CURRENT_REGISTERS

</td>
<td>
Current register values.

</td>
</tr>
<tr>
<td>
DEBUG_CURRENT_SOURCE_LINE

</td>
<td>
File name and line number of the source corresponding to the current instruction.

</td>
</tr>
</table>
 

Alternatively, <i>Flags</i> can be set to DEBUG_CURRENT_DEFAULT.  This value includes all of the above flags.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
Setting the flags contained in <i>Flags</i> merely allows the information to be printed.  The information will not always be printed (for example, it will not be printed if it is not available).

This is the same status information that is printed when breaking into the debugger.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.</p>