---
UID: NF:dbgeng.IDebugControl3.RemoveAssemblyOptions
title: IDebugControl3::RemoveAssemblyOptions method
author: windows-driver-content
description: The RemoveAssemblyOptions method turns off some of the assembly and disassembly options.
old-location: debugger\removeassemblyoptions.htm
old-project: debugger
ms.assetid: 0352b418-26ee-4f35-a171-1b456a115014
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugControl3, IDebugControl3 interface [Windows Debugging], RemoveAssemblyOptions method, IDebugControl3::RemoveAssemblyOptions, IDebugControl_8d971b27-ff9f-4097-a96a-68dabf08b200.xml, RemoveAssemblyOptions method [Windows Debugging], RemoveAssemblyOptions method [Windows Debugging], IDebugControl3 interface, RemoveAssemblyOptions,IDebugControl3.RemoveAssemblyOptions, dbgeng/IDebugControl3::RemoveAssemblyOptions, debugger.removeassemblyoptions
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
-	IDebugControl3.RemoveAssemblyOptions
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugControl3::RemoveAssemblyOptions method
The <b>RemoveAssemblyOptions</b> method turns off some of the assembly and disassembly options.

## Syntax

```
HRESULT RemoveAssemblyOptions(
  ULONG Options
);
```

## Parameters

`Options`

Specifies the assembly and disassembly options to turn off.  <i>Options</i> is a bit-set; the new value of the engine's options will equal the bitwise NOT of <i>Options</i> combined with the old value by using the bitwise AND operator (

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre></pre>
</td>
</tr>
</table></span></div>
).  For a description of the assembly and disassembly options, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541443">DEBUG_ASMOPT_XXX</a>.


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
 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

## Remarks

For more information about using assembly with the debugger engine API, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538127">Assembling and Disassembling Instructions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562128">.asm (Change Disassembly Options)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537852">AddAssemblyOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538121">Assemble</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541443">DEBUG_ASMOPT_XXX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541948">Disassemble</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545605">GetAssemblyOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556626">SetAssemblyOptions</a>