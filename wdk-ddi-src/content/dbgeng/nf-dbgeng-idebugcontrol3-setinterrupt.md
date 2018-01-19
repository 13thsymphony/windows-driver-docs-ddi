---
UID : NF:dbgeng.IDebugControl3.SetInterrupt
title : IDebugControl3::SetInterrupt method
author : windows-driver-content
description : The SetInterrupt method registers a user interrupt or breaks into the debugger.
old-location : debugger\setinterrupt.htm
old-project : debugger
ms.assetid : d67119c7-ecbe-446c-8a4f-38d33e92a277
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : IDebugControl3, IDebugControl3::SetInterrupt, SetInterrupt
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : dbgeng.h
req.include-header : Dbgeng.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IDebugControl.SetInterrupt,IDebugControl2.SetInterrupt,IDebugControl3.SetInterrupt
req.alt-loc : dbgeng.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# SetInterrupt method
The <b>SetInterrupt</b> method registers a user interrupt or breaks into the debugger.

## Syntax

````
HRESULT SetInterrupt(
  [in] ULONG Flags
);
````

## Parameters

`Flags`

Specifies the type of interrupt to register.  <i>Flags</i> can take one of the values listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_INTERRUPT_ACTIVE

</td>
<td>
If the target is running, the engine will request a break into the debugger.  This request might time out. For more information, see the "Remarks" section.

Otherwise, when the target is suspended, the engine will register a user interrupt.

</td>
</tr>
<tr>
<td>
DEBUG_INTERRUPT_PASSIVE

</td>
<td>
The engine will register a user interrupt.

</td>
</tr>
<tr>
<td>
DEBUG_INTERRUPT_EXIT

</td>
<td>
If there is currently a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561229">WaitForEvent</a> call running, the engine will force it to return.  If there are any debugger commands causing execution in the target -- for example, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549693">g (Go)</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff553496">p (Step)</a> -- the engine will force them to complete.  This does not force a break into the debugger, so the target might not be suspended. In which case, the <b>WaitForEvent</b> call will return E_PENDING.

Otherwise, when the target is suspended, register a user interrupt.

</td>
</tr>
</table>


## Return Value

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

## Remarks

This method can be called at any time and from any thread.  Once the interrupt has been registered, this method returns immediately.

If <i>Flags</i> is DEBUG_INTERRUPT_ACTIVE, and the interrupt times out, the engine will generate a synthetic exception event.  This event will be sent to event callback's <a href="https://msdn.microsoft.com/library/windows/hardware/ff550717">IDebugEventCallbacks::Exception</a> method.  The amount of time before the interrupt times out can be set using <a href="https://msdn.microsoft.com/library/windows/hardware/ff556725">SetInterruptTimeout</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546944">GetInterrupt</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546955">GetInterruptTimeout</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556725">SetInterruptTimeout</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::SetInterrupt method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>