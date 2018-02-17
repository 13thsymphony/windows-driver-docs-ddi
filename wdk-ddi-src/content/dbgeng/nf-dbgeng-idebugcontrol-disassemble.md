---
UID: NF:dbgeng.IDebugControl.Disassemble
title: IDebugControl::Disassemble method
author: windows-driver-content
description: The Disassemble method disassembles a processor instruction in the target's memory.
old-location: debugger\disassemble.htm
old-project: debugger
ms.assetid: a512c846-6896-48ca-a234-b9a30a3bff06
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: Disassemble, IDebugControl interface [Windows Debugging], Disassemble method, dbgeng/IDebugControl2::Disassemble, IDebugControl_7eb9fdc3-f2a0-4239-a035-9abb8e85cd28.xml, Disassemble method [Windows Debugging], IDebugControl2::Disassemble, dbgeng/IDebugControl3::Disassemble, debugger.disassemble, Disassemble method [Windows Debugging], IDebugControl interface, Disassemble method [Windows Debugging], IDebugControl2 interface, IDebugControl3 interface [Windows Debugging], Disassemble method, IDebugControl::Disassemble, Disassemble method [Windows Debugging], IDebugControl3 interface, dbgeng/IDebugControl::Disassemble, IDebugControl, IDebugControl3::Disassemble, IDebugControl2 interface [Windows Debugging], Disassemble method
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugControl.Disassemble
-	IDebugControl2.Disassemble
-	IDebugControl3.Disassemble
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# Disassemble method
The <b>Disassemble</b>  method disassembles a processor instruction in the target's memory.

## Syntax

````
HRESULT Disassemble(
  [in]            ULONG64  Offset,
  [in]            ULONG    Flags,
  [out, optional] PSTR     Buffer,
  [in]            ULONG    BufferSize,
  [out, optional] PULONG   DisassemblySize,
  [out]           PULONG64 EndOffset
);
````

## Parameters

`Offset`

Specifies the location in the target's memory of the instruction to disassemble.

`Flags`

Specifies the bit-flags that affect the behavior of this method.  Currently the only flag that can be set is DEBUG_DISASM_EFFECTIVE_ADDRESS; when set, the engine will compute the effective address from the current register information and display it.

`Buffer`

Receives the disassembled instruction.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

`BufferSize`

Specifies the size, in characters, of the <i>Buffer</i> buffer.

`DisassemblySize`

Receives the size, in characters, of the disassembled instruction.  If <i>DisassemblySize</i> is <b>NULL</b>, this information is not returned.

`EndOffset`

Receives the location in the target's memory of the instruction following the disassembled instruction.


## Return Value

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.  However, <i>Buffer</i> was too small to hold the disassembled instruction and the instruction was truncated to fit.

</td>
</tr>
</table>

## Remarks

The assembly language depends on the effective processor type of the target system.  For information about the assembly language, see the processor documentation.

The disassembly options--returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff545605">GetAssemblyOptions</a>--affect the operation of this method.

For an overview of using assembly in debugger applications, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540661">Debugging in Assembly Mode</a>.  For more information about using assembly with the debugger engine API, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538127">Assembling and Disassembling Instructions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/933a308c-61d1-4ca4-89c1-5749ba1b41c1">u (Unassemble)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538121">Assemble</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545605">GetAssemblyOptions</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::Disassemble method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>