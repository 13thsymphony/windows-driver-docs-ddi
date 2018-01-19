---
UID : NF:dbgeng.IDebugControl5.GetStackTraceEx
title : IDebugControl5::GetStackTraceEx method
author : windows-driver-content
description : The GetStackTraceEx method returns the frames at the top of the specified call stack. The GetStackTraceEx method provides inline frame support. For more information about working with inline functions, see Debugging Optimized Code and Inline Functions.
old-location : debugger\idebugcontrol5_getstacktraceex.htm
old-project : debugger
ms.assetid : 6DFCA3CB-D5DE-4EF5-892B-776B932E6CE6
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : IDebugControl5, IDebugControl5::GetStackTraceEx, GetStackTraceEx
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
req.alt-api : IDebugControl5.GetStackTraceEx
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


# GetStackTraceEx method
The GetStackTraceEx method returns the frames at the top of the specified call stack. The GetStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406275">Debugging Optimized Code and Inline Functions</a>.

## Syntax

````
HRESULT GetStackTraceEx(
  [in]            ULONG64               FrameOffset,
  [in]            ULONG64               StackOffset,
  [in]            ULONG64               InstructionOffset,
  [out]           PDEBUG_STACK_FRAME_EX Frames,
  [in]            ULONG                 FrameSize,
  [out, optional] PULONG                FramesFilled
);
````

## Parameters

`FrameOffset`

Specifies the location of the stack frame at the top of the stack.  If <i>FrameOffset</i> is set to zero, the current frame pointer is used instead.

`StackOffset`

Specifies the location of the current stack.  If <i>StackOffset</i> is set to zero, the current stack pointer is used instead.

`InstructionOffset`

Specifies the location of the instruction of interest for the function that is represented by the stack frame at the top of the stack.  If <i>InstructionOffset</i> is set to zero, the current instruction is used instead.

`Frames`

Receives the stack frames.  The number of elements this array holds is <i>FrameSize</i>.

`FramesSize`



`FramesFilled`

Receives the number of frames that were placed in the array <i>Frames</i>.  If <i>FramesFilled</i> is <b>NULL</b>, this information is not returned.


## Return Value

This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>No stack frames were returned.

## Remarks

The stack trace returned to Frames can be printed using <a href="https://msdn.microsoft.com/library/windows/hardware/dn818567">OutputStackTraceEx</a>.

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
<a href="..\dbgeng\nn-dbgeng-idebugcontrol5.md">IDebugControl5</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn818564">GetContextStackTraceEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546815">GetFrameOffset2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546933">GetInstructionOffset2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548414">GetStackOffset2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn818567">OutputStackTraceEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/1061015f-cb0c-490b-b256-e0dedb659f22">k, kb, kc, kd, kp, kP, kv (Display Stack Backtrace)</a>
</dt>
<dt>
<a href="..\wdbgexts\nc-wdbgexts-pwindbg_stacktrace_routine.md">StackTrace</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl5::GetStackTraceEx method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>