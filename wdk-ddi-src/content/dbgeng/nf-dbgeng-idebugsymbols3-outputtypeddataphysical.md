---
UID: NF.dbgeng.IDebugSymbols3.OutputTypedDataPhysical
title: IDebugSymbols3::OutputTypedDataPhysical method
author: windows-driver-content
description: The OutputTypedDataPhysical method formats the contents of a variable in the target computer's physical memory, and then sends this to the output callbacks.
old-location: debugger\outputtypeddataphysical.htm
old-project: Debugger
ms.assetid: 0c2ae1ff-bbf1-462f-b9ab-49f74cf12fae
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IDebugSymbols3, IDebugSymbols3::OutputTypedDataPhysical, OutputTypedDataPhysical
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
req.alt-api: IDebugSymbols.OutputTypedDataPhysical,IDebugSymbols2.OutputTypedDataPhysical,IDebugSymbols3.OutputTypedDataPhysical
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

# IDebugSymbols3::OutputTypedDataPhysical method



## -description
The <b>OutputTypedDataPhysical</b> method formats the contents of a variable in the target computer's physical memory, and then sends this to the <a href="debugger.using_input_and_output#output_callbacks#output_callbacks">output callbacks</a>.



## -syntax

````
HRESULT OutputTypedDataPhysical(
  [in] ULONG   OutputControl,
  [in] ULONG64 Offset,
  [in] ULONG64 Module,
  [in] ULONG   TypeId,
  [in] ULONG   Flags
);
````


## -parameters

### -param OutputControl [in]

Specifies the output control used to determine which output callbacks can receive the output.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a> for possible values.


### -param Offset [in]

Specifies the physical address in the target computer's memory of the variable.


### -param Module [in]

Specifies the base address of the module containing the type of the variable.


### -param TypeId [in]

Specifies the type ID of the type of the variable.


### -param Flags [in]

Specifies the bit-set containing the formatting options.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541712">DEBUG_TYPEOPTS_XXX</a> for possible values.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
This method is only available in kernel mode debugging.

The output produced by this method is the same as for the debugger command <b>DT</b>.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff542772">dt (Display Type)</a>.

For more information about types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558931">Types</a>.  For information about output, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.


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