---
UID: NF:dbgeng.IDebugSymbols3.OutputTypedDataVirtual
title: IDebugSymbols3::OutputTypedDataVirtual method
author: windows-driver-content
description: The OutputTypedDataVirtual method formats the contents of a variable in the target's virtual memory, and then sends this to the output callbacks.
old-location: debugger\outputtypeddatavirtual.htm
old-project: debugger
ms.assetid: d6faa4ee-2fdb-425a-81db-8257285ba47d
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3::OutputTypedDataVirtual, OutputTypedDataVirtual
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
req.alt-api: IDebugSymbols.OutputTypedDataVirtual,IDebugSymbols2.OutputTypedDataVirtual,IDebugSymbols3.OutputTypedDataVirtual
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

# IDebugSymbols3::OutputTypedDataVirtual method



## -description
The <b>OutputTypedDataVirtual</b> method formats the contents of a variable in the target's virtual memory, and then sends this to the <a href="debugger.using_input_and_output#output_callbacks#output_callbacks">output callbacks</a>.



## -syntax

````
HRESULT OutputTypedDataVirtual(
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

Specifies the location in the target's virtual address space of the variable.


### -param Module [in]

Specifies the base address of the module containing the type.


### -param TypeId [in]

Specifies the type ID of the type.


### -param Flags [in]

Specifies the formatting flags.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541712">DEBUG_TYPEOPTS_XXX</a> for possible values.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
The output produced by this method is the same as for the debugger command <b>DT</b>.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff542772">dt (Display Type)</a>.

For more information about types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558931">Types</a>.  For more information about output, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.</p>