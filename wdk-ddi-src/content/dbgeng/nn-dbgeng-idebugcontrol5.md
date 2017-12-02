---
UID: NN.dbgeng.IDebugControl5
title: IDebugControl5
author: windows-driver-content
description: .
old-location: debugger\idebugcontrol5.htm
old-project: debugger
ms.assetid: 6C358D49-970D-4687-B16E-7D1B44CB0A8E
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugSystemObjects4, SetImplicitThreadDataOffset, IDebugSystemObjects4::SetImplicitThreadDataOffset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugControl5
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
req.iface: IDebugSystemObjects4
---

# IDebugControl5 interface



## -description
<p></p>


## -inheritance
<p>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugControl5</b> interface inherits from <a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>. <b>IDebugControl5</b> also has these types of members:</p>

<p>The <b>IDebugControl5</b> interface has these methods.</p>

<p>The GetBreakpointByGuid method returns the breakpoint with the specified breakpoint GUID.</p>

<p>The GetContextStackTraceEx method returns the frames at the top of the call stack, starting with an arbitrary <a href="debugger.changing_contexts#register_context#register_context">register context</a> and returning the reconstructed register context for each stack frame. The GetContextStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406275">Debugging Optimized Code and Inline Functions</a>.</p>

<p>The GetStackTraceEx method returns the frames at the top of the specified call stack. The GetStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406275">Debugging Optimized Code and Inline Functions</a>.</p>

<p>The OutputContextStackTraceEx method prints the call stack specified by an array of stack frames and corresponding register contexts. The OutputContextStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406275">Debugging Optimized Code and Inline Functions</a>.</p>

<p>The OutputStackTraceEx method outputs either the supplied stack frame or the current stack frames.   The OutputStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406275">Debugging Optimized Code and Inline Functions</a>.</p>

<p> </p>

## -members
<p>The <b>IDebugControl5</b> interface has these methods.</p><table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.idebugcontrol5_getbreakpointbyguid">GetBreakpointByGuid</a>
</td>
<td align="left" width="63%">
<p>The GetBreakpointByGuid method returns the breakpoint with the specified breakpoint GUID.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.idebugcontrol5_getcontextstacktraceex">GetContextStackTraceEx</a>
</td>
<td align="left" width="63%">
<p>The GetContextStackTraceEx method returns the frames at the top of the call stack, starting with an arbitrary <a href="debugger.changing_contexts#register_context#register_context">register context</a> and returning the reconstructed register context for each stack frame. The GetContextStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406275">Debugging Optimized Code and Inline Functions</a>.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.idebugcontrol5_getstacktraceex">GetStackTraceEx</a>
</td>
<td align="left" width="63%">
<p>The GetStackTraceEx method returns the frames at the top of the specified call stack. The GetStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406275">Debugging Optimized Code and Inline Functions</a>.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.idebugcontrol5_outputcontextstacktraceex">OutputContextStackTraceEx</a>
</td>
<td align="left" width="63%">
<p>The OutputContextStackTraceEx method prints the call stack specified by an array of stack frames and corresponding register contexts. The OutputContextStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406275">Debugging Optimized Code and Inline Functions</a>.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.idebugcontrol5_outputstacktraceex">OutputStackTraceEx</a>
</td>
<td align="left" width="63%">
<p>The OutputStackTraceEx method outputs either the supplied stack frame or the current stack frames.   The OutputStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406275">Debugging Optimized Code and Inline Functions</a>.</p>
</td>
</tr>
</table><p>The GetBreakpointByGuid method returns the breakpoint with the specified breakpoint GUID.</p>

<p>The GetContextStackTraceEx method returns the frames at the top of the call stack, starting with an arbitrary <a href="debugger.changing_contexts#register_context#register_context">register context</a> and returning the reconstructed register context for each stack frame. The GetContextStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406275">Debugging Optimized Code and Inline Functions</a>.</p>

<p>The GetStackTraceEx method returns the frames at the top of the specified call stack. The GetStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406275">Debugging Optimized Code and Inline Functions</a>.</p>

<p>The OutputContextStackTraceEx method prints the call stack specified by an array of stack frames and corresponding register contexts. The OutputContextStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406275">Debugging Optimized Code and Inline Functions</a>.</p>

<p>The OutputStackTraceEx method outputs either the supplied stack frame or the current stack frames.   The OutputStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406275">Debugging Optimized Code and Inline Functions</a>.</p>

<p> </p>

## -remarks


## -requirements
<table>
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

## -see-also
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
<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl5 interface%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
