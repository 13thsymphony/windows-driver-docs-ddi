---
UID : NF:dbgeng.IDebugControl5.OutputStackTraceEx
title : IDebugControl5::OutputStackTraceEx method
author : windows-driver-content
description : The OutputStackTraceEx method outputs either the supplied stack frame or the current stack frames.
old-location : debugger\idebugcontrol5_outputstacktraceex.htm
old-project : debugger
ms.assetid : C89203F9-FCCF-4D71-8E8A-9F5F4AE89004
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : IDebugControl5, IDebugControl5::OutputStackTraceEx, OutputStackTraceEx
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
req.alt-api : IDebugControl5.OutputStackTraceEx
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


# OutputStackTraceEx method
The OutputStackTraceEx method outputs either the supplied stack frame or the current stack frames.   The OutputStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406275">Debugging Optimized Code and Inline Functions</a>.

## Syntax

````
HRESULT OutputStackTraceEx(
  [in]           ULONG                 OutputControl,
  [in, optional] PDEBUG_STACK_FRAME_EX Frames,
  [in]           ULONG                 FramesSize,
  [in]           ULONG                 Flags
);
````

## Parameters

`OutputControl`

Specifies where to send the output.  For possible values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a>.

`Frames`

Specifies the array of stack frames to output.  The number of elements in this array is <i>FramesSize</i>.  If <i>Frames</i> is <b>NULL</b>, the current stack frames are used.

`FramesSize`

Specifies the number of frames to output.

`Flags`

Specifies bit flags that determine what information to output for each frame.  <i>Flags</i> can be any combination of values from the following table.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_STACK_ARGUMENTS

</td>
<td>
Displays the first three pieces of stack memory at the frame of each call.  On platforms where parameters are passed on the stack, and the code for the frame uses stack arguments, these values will be the arguments to the function.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_FUNCTION_INFO

</td>
<td>
Displays information about the function that corresponds to the frame.  This includes calling convention and frame pointer omission (FPO) information.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_SOURCE_LINE

</td>
<td>
Displays source line information for each frame of the stack trace.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_FRAME_ADDRESSES

</td>
<td>
Displays the return address, previous frame address, and other relevant addresses for each frame.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_COLUMN_NAMES

</td>
<td>
Displays column names.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_NONVOLATILE_REGISTERS

</td>
<td>
Displays the non-volatile register context for each frame.  This is only meaningful for some platforms.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_FRAME_NUMBERS

</td>
<td>
Displays frame numbers.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_PARAMETERS

</td>
<td>
Displays parameter names and values as given in symbol information.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_FRAME_ADDRESSES_RA_ONLY

</td>
<td>
Displays just the return address in stack frame addresses.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_FRAME_MEMORY_USAGE

</td>
<td>
Displays the number of bytes that separate the frames.

</td>
</tr>
<tr>
<td>
DEBUG_STACK_PARAMETERS_NEWLINE

</td>
<td>
Displays each parameter and its type and value on a new line.

</td>
</tr>
</table>


## Return Value

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

## Remarks

The array of stack frames can be obtained using <a href="https://msdn.microsoft.com/library/windows/hardware/dn818565">GetStackTraceEx</a>.

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
<a href="https://msdn.microsoft.com/library/windows/hardware/dn818565">GetStackTraceEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/1061015f-cb0c-490b-b256-e0dedb659f22">k, kb, kc, kd, kp, kP, kv (Display Stack Backtrace)</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl5::OutputStackTraceEx method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>