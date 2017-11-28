---
UID: NF.dbgeng.IDebugBreakpoint.SetMatchThreadId
title: IDebugBreakpoint::SetMatchThreadId
author: windows-driver-content
description: The SetMatchThreadId method sets the engine thread ID of the thread that can trigger a breakpoint.
old-location: debugger\setmatchthreadid.htm
old-project: debugger
ms.assetid: 66170e28-24db-4125-bd4e-ef07e8e82e79
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: IDebugBreakpoint, SetMatchThreadId, IDebugBreakpoint::SetMatchThreadId
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
req.alt-api: IDebugBreakpoint.SetMatchThreadId,IDebugBreakpoint2.SetMatchThreadId
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
req.iface: IDebugBreakpoint
---

# IDebugBreakpoint::SetMatchThreadId method



## -description
<p>The <b>SetMatchThreadId</b> method sets the engine thread ID of the thread that can trigger a breakpoint.</p>


## -syntax

````
HRESULT SetMatchThreadId(
  [in] ULONG Thread
);
````


## -parameters
<dl>

### -param <i>Thread</i> [in]

<dd>
<p>The engine thread ID of the thread that can trigger this breakpoint.</p>
</dd>
</dl>

## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p><dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl><p>The thread that <i>Thread</i> specifies could not be found.</p><dl>
<dt><b>E_INVALIDARG</b></dt>
</dl><p>The target is in a kernel and the breakpoint is a processor breakpoint.  Processor breakpoints cannot be limited to threads in kernel mode.</p>

<p> </p>

<p>This method can also return other error values.  For more information, see <a href="debugger.hresult_values">Return Values</a>.</p>

## -remarks
<p>If you have set a thread for the breakpoint, the breakpoint can be triggered only if that thread hits the breakpoint.  If you have not set a thread, any thread can trigger the breakpoint.</p>

<p>If you have set a thread, you can remove the setting by setting <i>Id</i> to DEBUG_ANY_ID.</p>

<p>For more information about breakpoint properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.</p>

<p>If you have set a thread for the breakpoint, the breakpoint can be triggered only if that thread hits the breakpoint.  If you have not set a thread, any thread can trigger the breakpoint.</p>

<p>If you have set a thread, you can remove the setting by setting <i>Id</i> to DEBUG_ANY_ID.</p>

<p>For more information about breakpoint properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.</p>

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