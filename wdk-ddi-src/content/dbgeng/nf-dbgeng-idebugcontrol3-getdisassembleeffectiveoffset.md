---
UID: NF:dbgeng.IDebugControl3.GetDisassembleEffectiveOffset
title: IDebugControl3::GetDisassembleEffectiveOffset method
author: windows-driver-content
description: The GetDisassembleEffectiveOffset method returns the address of the last instruction disassembled using Disassemble.
old-location: debugger\getdisassembleeffectiveoffset.htm
old-project: debugger
ms.assetid: 07f652f2-d370-4f88-a7f0-f6946fd50c79
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugControl2, IDebugControl_5593ec3a-31f4-4775-9356-49f1757323c0.xml, GetDisassembleEffectiveOffset method [Windows Debugging], IDebugControl::GetDisassembleEffectiveOffset, debugger.getdisassembleeffectiveoffset, GetDisassembleEffectiveOffset method [Windows Debugging], IDebugControl2 interface, IDebugControl2 interface [Windows Debugging], GetDisassembleEffectiveOffset method, dbgeng/IDebugControl2::GetDisassembleEffectiveOffset, IDebugControl3, GetDisassembleEffectiveOffset method [Windows Debugging], IDebugControl interface, IDebugControl3::GetDisassembleEffectiveOffset, IDebugControl, IDebugControl interface [Windows Debugging], GetDisassembleEffectiveOffset method, IDebugControl3 interface [Windows Debugging], GetDisassembleEffectiveOffset method, GetDisassembleEffectiveOffset, IDebugControl2::GetDisassembleEffectiveOffset, dbgeng/IDebugControl3::GetDisassembleEffectiveOffset, dbgeng/IDebugControl::GetDisassembleEffectiveOffset, GetDisassembleEffectiveOffset method [Windows Debugging], IDebugControl3 interface
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
-	IDebugControl.GetDisassembleEffectiveOffset
-	IDebugControl2.GetDisassembleEffectiveOffset
-	IDebugControl3.GetDisassembleEffectiveOffset
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetDisassembleEffectiveOffset method
The <b>GetDisassembleEffectiveOffset</b> method returns the address of the last instruction disassembled using <a href="https://msdn.microsoft.com/library/windows/hardware/ff541948">Disassemble</a>.

## Syntax

````
HRESULT GetDisassembleEffectiveOffset(
  [out] PULONG64 Offset
);
````

## Parameters

`Offset`

Receives the address in the target's memory of the effective offset from the last instruction disassembled.


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
</table>

## Remarks

The effective offset is the memory location used by an instruction.  For example, if the last instruction to be disassembled is <code>move ax, [ebp+4]</code>, the effective address is the value of <code>ebp+4</code>.  This corresponds to the <b>$ea</b> pseudo-register.

For more information about using assembly with the debugger engine API, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538127">Assembling and Disassembling Instructions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541948">Disassemble</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetDisassembleEffectiveOffset method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>