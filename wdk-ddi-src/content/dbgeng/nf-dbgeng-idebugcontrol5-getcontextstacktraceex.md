---
UID: NF:dbgeng.IDebugControl5.GetContextStackTraceEx
title: IDebugControl5::GetContextStackTraceEx method
author: windows-driver-content
description: The GetContextStackTraceEx method returns the frames at the top of the call stack, starting with an arbitrary register context and returning the reconstructed register context for each stack frame.
old-location: debugger\idebugcontrol5_getcontextstacktraceex.htm
old-project: debugger
ms.assetid: 26B191ED-A38B-412D-93C3-E9A55216F91E
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetContextStackTraceEx method [Windows Debugging], GetContextStackTraceEx method [Windows Debugging], IDebugControl5 interface, GetContextStackTraceEx,IDebugControl5.GetContextStackTraceEx, IDebugControl5, IDebugControl5 interface [Windows Debugging], GetContextStackTraceEx method, IDebugControl5::GetContextStackTraceEx, dbgeng/IDebugControl5::GetContextStackTraceEx, debugger.idebugcontrol5_getcontextstacktraceex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h, Ntddk.h
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
-	IDebugControl5.GetContextStackTraceEx
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetContextStackTraceEx method
The GetContextStackTraceEx method returns the frames at the top of the call stack, starting with an arbitrary <a href="https://msdn.microsoft.com/3690903c-4281-4c65-98b0-00ca22206168">register context</a> and returning the reconstructed register context for each stack frame. The GetContextStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406275">Debugging Optimized Code and Inline Functions</a>.

## Syntax

````
HRESULT GetContextStackTraceEx(
  [in, optional]  PVOID                 StartContext,
  [in]            ULONG                 StartContextSize,
  [out, optional] PDEBUG_STACK_FRAME_EX Frames,
  [in]            ULONG                 FramesSize,
  [out, optional] PVOID                 FrameContexts,
  [in]            ULONG                 FrameContextsSize,
  [in]            ULONG                 FrameContextsEntrySize,
  [out, optional] PULONG                FramesFilled
);
````

## Parameters

`StartContext`

Specifies the register context for the top of the stack.

`StartContextSize`

Specifies the size, in bytes, of the <i>StartContext</i> register context.

`Frames`

Receives the stack frames.  The number of elements this array holds is <i>FrameSize</i>.  If <i>Frames</i> is <b>NULL</b>, this information is not returned.

`FramesSize`

Specifies the number of items in the array <i>Frames</i>.

`FrameContexts`

Receives the reconstructed register context for each frame in the stack.  The entries in this array correspond to the entries in the <i>Frames</i> array.  The type of the thread context is the CONTEXT structure for the target's effective processor.  If <i>FrameContexts</i> is <b>NULL</b>, this information is not returned.

`FrameContextsSize`

Specifies the size, in bytes, of the memory pointed to by <i>FrameContexts</i>.  The number of stack frames returned equals the number of contexts returned, and <i>FrameContextsSize</i> must equal <i>FramesSize</i> times <i>FrameContextsEntrySize</i>.

`FrameContextsEntrySize`

Specifies the size, in bytes, of each frame context in <i>FrameContexts</i>.

`FramesFilled`

Receives the number of frames that were placed in the array <i>Frames</i> and contexts in <i>FrameContexts</i>.  If <i>FramesFilled</i> is <b>NULL</b>, this information is not returned.


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
 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.

## Remarks

The stack trace returned to <i>Frames</i> and <i>FrameContexts</i> can be printed using <a href="https://msdn.microsoft.com/library/windows/hardware/dn818566">OutputContextStackTraceEx</a>.

It is common for stack unwinds to restore only a subset of the registers.  For example, stack unwinds will not always restore the volatile register state because the volatile registers are scratch registers and code does not need to preserve them.  Registers that are not restored on unwind are left as the last value restored, so care should be taken when using the register state that might not be restored by an unwind.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h, Ntddk.h) |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol5.md">IDebugControl5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn818566">OutputContextStackTraceEx</a>



<a href="https://msdn.microsoft.com/1061015f-cb0c-490b-b256-e0dedb659f22">k, kb, kc, kd, kp, kP, kv (Display Stack Backtrace)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn818565">GetStackTraceEx</a>