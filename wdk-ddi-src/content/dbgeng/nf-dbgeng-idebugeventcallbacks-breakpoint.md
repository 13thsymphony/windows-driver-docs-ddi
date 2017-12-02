---
UID: NF.dbgeng.IDebugEventCallbacks.Breakpoint
title: IDebugEventCallbacks::Breakpoint
author: windows-driver-content
description: The Breakpoint callback method is called by the engine when the target issues a breakpointexception.
old-location: debugger\idebugeventcallbacks_breakpoint.htm
old-project: debugger
ms.assetid: 76b9aca2-4630-45e2-bed4-f701018c86a5
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugEventCallbacks, Breakpoint, IDebugEventCallbacks::Breakpoint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugEventCallbacks.Breakpoint
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
req.iface: IDebugEventCallbacks
---

# IDebugEventCallbacks::Breakpoint method



## -description
<p>The <b>Breakpoint</b> callback method is called by the engine when the target issues a breakpoint<a href="wdkgloss.e#wdkgloss.exception#wdkgloss.exception"><i>exception</i></a>.</p>


## -syntax

````
HRESULT Breakpoint(
  [in] PDEBUG_BREAKPOINT Bp
);
````


## -parameters
<dl>

### -param Bp [in]

<dd>
<p>Specifies a pointer to the <a href="..\dbgeng\nn-dbgeng-idebugbreakpoint.md">IDebugBreakpoint</a> object corresponding to the breakpoint that was triggered.</p>
</dd>
</dl>

## -returns
<p>This method returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.</p>

## -remarks
<p>If the breakpoint has an associated command, the engine executes that command before calling this method.</p>

<p>The engine will only call this method if an <a href="..\dbgeng\nn-dbgeng-idebugbreakpoint.md">IDebugBreakpoint</a> object corresponding to the breakpoint exists in the engine, and--if the breakpoint is a private breakpoint--this <a href="..\dbgeng\nn-dbgeng-idebugeventcallbacks.md">IDebugEventCallbacks</a> object was registered with the client that added the breakpoint.</p>

<p>The engine calls this method only if the DEBUG_EVENT_BREAKPOINT flag is set in the mask returned by <a href="debugger.idebugeventcallbacks_getinterestmask">IDebugEventCallbacks::GetInterestMask</a>.</p>

<p>Because the engine deletes the corresponding <b>IDebugBreakpoint</b> object when a breakpoint is removed (for example, by using <a href="debugger.removebreakpoint">RemoveBreakpoint</a>), the value of <i>Bp</i> might be invalid after <b>Breakpoint</b> returns.  Therefore, implementations of <b>IDebugEventCallbacks</b> should not access <i>Bp</i> after <b>Breakpoint</b> returns.</p>

<p>For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.  For information about managing breakpoints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538928">Breakpoints</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>