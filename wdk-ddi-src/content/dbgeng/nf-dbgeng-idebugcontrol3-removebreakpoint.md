---
UID : NF:dbgeng.IDebugControl3.RemoveBreakpoint
title : IDebugControl3::RemoveBreakpoint method
author : windows-driver-content
description : The RemoveBreakpoint method removes a breakpoint.
old-location : debugger\removebreakpoint.htm
old-project : debugger
ms.assetid : ce0f5e42-3f4e-48e1-9e73-96bca96e8e23
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : IDebugControl3::RemoveBreakpoint, IDebugControl2::RemoveBreakpoint, RemoveBreakpoint method [Windows Debugging], IDebugControl interface, dbgeng/IDebugControl2::RemoveBreakpoint, IDebugControl_431f31ce-38fb-4350-851b-49b103047943.xml, IDebugControl3, RemoveBreakpoint method [Windows Debugging], IDebugControl2 interface [Windows Debugging], RemoveBreakpoint method, IDebugControl interface [Windows Debugging], RemoveBreakpoint method, debugger.removebreakpoint, dbgeng/IDebugControl::RemoveBreakpoint, IDebugControl3 interface [Windows Debugging], RemoveBreakpoint method, RemoveBreakpoint method [Windows Debugging], IDebugControl2 interface, dbgeng/IDebugControl3::RemoveBreakpoint, IDebugControl::RemoveBreakpoint, RemoveBreakpoint, RemoveBreakpoint method [Windows Debugging], IDebugControl3 interface
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
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : dbgeng.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# RemoveBreakpoint method
The <b>RemoveBreakpoint</b>  method removes a breakpoint.

## Syntax

````
HRESULT RemoveBreakpoint(
  [in] PDEBUG_BREAKPOINT Bp
);
````

## Parameters

`Bp`

Specifies an interface pointer to breakpoint to remove.


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

This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

## Remarks

After <b>RemoveBreakpoint</b> and <b>RemoveBreakpoint2</b> are called, the breakpoint object specified in the <i>Bp</i> parameter must not be used again.
<div class="alert"><b>Note</b>    Even though <a href="..\dbgeng\nn-dbgeng-idebugbreakpoint.md">IDebugBreakpoint</a> extends the COM interface <b>IUnknown</b>, the lifetime of the breakpoint is not controlled using the <b>IUnknown</b> interface.  Instead, the breakpoint is deleted after <b>RemoveBreakpoint</b> and <b>RemoveBreakpoint2</b> are called.</div><div> </div>For more details, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>.

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

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537856">AddBreakpoint</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>

<a href="..\dbgeng\nn-dbgeng-idebugbreakpoint.md">IDebugBreakpoint</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::RemoveBreakpoint method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>