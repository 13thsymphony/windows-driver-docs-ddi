---
UID: NF:dbgeng.IDebugEventCallbacksWide.Breakpoint
title: IDebugEventCallbacksWide::Breakpoint method
author: windows-driver-content
description: The Breakpoint callback method is called by the engine when the target issues a breakpointexception.
old-location: debugger\idebugeventcallbackswide_breakpoint.htm
old-project: debugger
ms.assetid: ee9b9b6c-c76e-4979-9f23-c411fe1b002a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugEventCallbacksWide, IDebugEventCallbacksWide::Breakpoint, Breakpoint
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
req.alt-api: IDebugEventCallbacksWide.Breakpoint
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

# IDebugEventCallbacksWide::Breakpoint method



## -description
The <b>Breakpoint</b> callback method is called by the engine when the target issues a breakpoint<a href="wdkgloss.e#wdkgloss.exception#wdkgloss.exception"><i>exception</i></a>.



## -syntax

````
HRESULT Breakpoint(
  [in] PDEBUG_BREAKPOINT2 Bp
);
````


## -parameters

### -param Bp [in]

Specifies a pointer to the <a href="..\dbgeng\nn-dbgeng-idebugbreakpoint.md">IDebugBreakpoint</a> object corresponding to the breakpoint that was triggered.


## -returns
This method returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.


## -remarks
If the breakpoint has an associated command, the engine executes that command before calling this method.

The engine will only call this method if an <a href="..\dbgeng\nn-dbgeng-idebugbreakpoint.md">IDebugBreakpoint</a> object corresponding to the breakpoint exists in the engine, and--if the breakpoint is a private breakpoint--this <a href="..\dbgeng\nn-dbgeng-idebugeventcallbackswide.md">IDebugEventCallbacksWide</a> object was registered with the client that added the breakpoint.

The engine calls this method only if the DEBUG_EVENT_BREAKPOINT flag is set in the mask returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550625">IDebugEventCallbacksWide::GetInterestMask</a>.

Because the engine deletes the corresponding <b>IDebugBreakpoint</b> object when a breakpoint is removed (for example, by using <a href="https://msdn.microsoft.com/library/windows/hardware/ff554487">RemoveBreakpoint</a>), the value of <i>Bp</i> might be invalid after <b>Breakpoint</b> returns.  Therefore, implementations of <b>IDebugEventCallbacksWide</b> should not access <i>Bp</i> after <b>Breakpoint</b> returns.

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.  For information about managing breakpoints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538928">Breakpoints</a>.


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