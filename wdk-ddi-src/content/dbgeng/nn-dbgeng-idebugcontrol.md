---
UID: NN.dbgeng.IDebugControl
title: IDebugControl
author: windows-driver-content
description: IDebugControl interface
old-location: debugger\idebugcontrol.htm
old-project: debugger
ms.assetid: 6ff5b9ff-d2b8-4ade-8b8b-20284efdf266
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: DebugCreateEx
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
req.alt-api: IDebugControl,IDebugControl.GetWindbgExtensionApis32
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
---

# IDebugControl interface



## -description

## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugControl</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IDebugControl</b> also has these types of members:

The <b>IDebugControl</b> interface has these methods.

Creates a new breakpoint for the current target.


 Turns on some of the debugger engine's options.

Loads an extension library into the debugger engine.


Assembles a single processor instruction. The assembled instruction is placed in the target's memory.

Calls a debugger extension.

Closes the currently-open log file.

Converts a value of one type into a value of another type.


Converts an array of values into an array of values of different types.

Formats a string and sends the result to output callbacks that were registered with some of the engine's clients.


Formats a string and sends the result to output callbacks that were registered with some of the engine's clients.


Disassembles a processor instruction in the target's memory.


Evaluates an expression, returning the result.

Executes the specified debugger commands.


Opens the specified file and executes the debugger commands that are contained within.


Returns the processor type of the physical processor of the computer that is running the target.


Returns the breakpoint with the specified breakpoint ID.


Returns the breakpoint located at the specified index.


Returns the parameters of one or more breakpoints.


Returns the current code level and is mainly used when stepping through code.


Describes the nature of the current target.


Returns the address of the last instruction disassembled using Disassemble.


Returns the effective processor type of the processor of the computer that is running the target.


Returns the engine's options.

Returns the debugger command that the engine will execute when a specified event occurs.


Returns a short description of an event for a specific filter.


Returns the parameters for exception filters specified by exception codes or by index.


Returns the command that will be executed by the debugger engine upon the second chance of a specified exception.


Returns the executing processor type for the processor for which the last event occurred.


Returns information about the execution status of the debugger engine.


Returns the handle for an already loaded extension library.


Returns a pointer to an extension function from an extension library.


Checks whether a user interrupt was issued.

Returns the number of seconds that the engine will wait when requesting a break into the debugger.

Returns information about the last event that occurred in a target.


Returns the name of the currently open log file.

Returns the output mask for the currently open log file.

HRESULT



Returns the location of a processor instruction relative to a given location.


Receives the handle of the event that will be signaled after the next exception in a target.


Returns the number of breakpoints for the current process.


Returns the number of event filters currently used by the engine.


Returns the number of processor types that are supported by the computer running the current target.

Returns the number of processors on the computer running the current target.


Returns the number of processor types supported by the engine.


Returns the page size for the effective processor mode.

Returns the processor types that are supported by the computer running the current target.


Returns the full name and abbreviated name of the specified processor type.


Returns the standard prompt text that will be prepended to the formatted output specified in the <b>OutputPrompt</b> and <b>OutputPromptVaList</b> methods.

Returns the default radix (number base) used by the debugger engine when it evaluates and displays MASM expressions, and when it displays symbol information.

 Returns the return address for the current function.

Returns the value of filter argument for thespecific filters that have an argument.


Returns the parameters for specific event filters.


Returns the frames at the top of the specified call stack.

Returns the processor types supported by the debugger engine. 


Returns the control values for handling system errors.


Returns information that identifies the operating system on the computer that is running the current target.

Returns the value of a fixed-name alias.



returns a structure that facilitates using the WdbgExts API.


Requests an input string from the debugger engine.


Determines if the effective processor uses 64-bit pointers.

Opens a log file that will receive output from the client objects.

Formats a string and sends the result to output callbacks that have been registered with the engine's clients.

Prints the current state of the current target to the debugger console.


Disassembles a processor instruction and sends the disassembly to the output callbacks.


Disassembles several processor instructions and sends the resulting assembly instructions to the output callbacks.

 Formats and sends a user prompt to the output callback objects.


Formats and sends a user prompt to the output callback objects.


Outputs either the supplied stack frame or the current stack frames.


 Formats a string and sends the result to the output callbacks that are registered with the engine's clients.


Prints version information about the debugger engine to the debugger console.


Reads the kernel bug check code and related parameters.


Removes a breakpoint.


Turns off some of the engine's options.


Unloads an extension library.

This method is used by <a href="..\dbgeng\nn-dbgeng-idebuginputcallbacks.md">IDebugInputCallbacks</a> objects to send an input string to the engine following a request for input.


Sets the current code level and is mainly used when stepping through code.


Sets the effective processor type of the processor of the computer that is running the target.


Changes the engine's options.


Sets a debugger command for the engine to execute when a specified event occurs.


Changes the break status and handling status for some exception filters.


Sets the command that will be executed by the debugger engine on the second chance of a specified exception.

Requests that the debugger engine enter an executable state. Actual execution will not occur until the next time <b>WaitForEvent</b> is called.


Registers a user interrupt or breaks into the debugger.

Sets the number of seconds that the debugger engine should wait when requesting a break into the debugger.

Sets the output mask for the currently open log file.


Sets the event that will be signaled after the next exception in a target.


Sets the default radix (number base) used by the debugger engine when it evaluates and displays MASM expressions, and when it displays symbol information.

Sets the value of filter argument for the specific filters that can have an argument.


Changes the break status and handling status for some specific event filters.


Sets the control values for handling system errors.

Sets the value of a fixed-name alias.

Waits for an event that breaks into the debugger engine application.


 


## -members
The <b>IDebugControl</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.addbreakpoint">AddBreakpoint</a>
</td>
<td align="left" width="63%">
Creates a new breakpoint for the current target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.addengineoptions">AddEngineOptions</a>
</td>
<td align="left" width="63%">
 Turns on some of the debugger engine's options.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.addextension">AddExtension</a>
</td>
<td align="left" width="63%">
Loads an extension library into the debugger engine.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.assemble">Assemble</a>
</td>
<td align="left" width="63%">
Assembles a single processor instruction. The assembled instruction is placed in the target's memory.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.callextension">CallExtension</a>
</td>
<td align="left" width="63%">
Calls a debugger extension.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.closelogfile">CloseLogFile</a>
</td>
<td align="left" width="63%">
Closes the currently-open log file.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.coercevalue">CoerceValue</a>
</td>
<td align="left" width="63%">
Converts a value of one type into a value of another type.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.coercevalues">CoerceValues</a>
</td>
<td align="left" width="63%">
Converts an array of values into an array of values of different types.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.controlledoutput">ControlledOutput</a>
</td>
<td align="left" width="63%">
Formats a string and sends the result to output callbacks that were registered with some of the engine's clients.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.controlledoutputvalist">ControlledOutputVaList</a>
</td>
<td align="left" width="63%">
Formats a string and sends the result to output callbacks that were registered with some of the engine's clients.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.disassemble">Disassemble</a>
</td>
<td align="left" width="63%">
Disassembles a processor instruction in the target's memory.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.evaluate">Evaluate</a>
</td>
<td align="left" width="63%">
Evaluates an expression, returning the result.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.execute">Execute</a>
</td>
<td align="left" width="63%">
Executes the specified debugger commands.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.executecommandfile">ExecuteCommandFile</a>
</td>
<td align="left" width="63%">
Opens the specified file and executes the debugger commands that are contained within.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getactualprocessortype">GetActualProcessorType</a>
</td>
<td align="left" width="63%">
Returns the processor type of the physical processor of the computer that is running the target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getbreakpointbyid">GetBreakpointById</a>
</td>
<td align="left" width="63%">
Returns the breakpoint with the specified breakpoint ID.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getbreakpointbyindex">GetBreakpointByIndex</a>
</td>
<td align="left" width="63%">
Returns the breakpoint located at the specified index.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getbreakpointparameters">GetBreakpointParameters</a>
</td>
<td align="left" width="63%">
Returns the parameters of one or more breakpoints.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getcodelevel">GetCodeLevel</a>
</td>
<td align="left" width="63%">
Returns the current code level and is mainly used when stepping through code.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getdebuggeetype">GetDebuggeeType</a>
</td>
<td align="left" width="63%">
Describes the nature of the current target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getdisassembleeffectiveoffset">GetDisassembleEffectiveOffset</a>
</td>
<td align="left" width="63%">
Returns the address of the last instruction disassembled using Disassemble.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.geteffectiveprocessortype">GetEffectiveProcessorType</a>
</td>
<td align="left" width="63%">
Returns the effective processor type of the processor of the computer that is running the target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getengineoptions">GetEngineOptions</a>
</td>
<td align="left" width="63%">
Returns the engine's options.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.geteventfiltercommand">GetEventFilterCommand</a>
</td>
<td align="left" width="63%">
Returns the debugger command that the engine will execute when a specified event occurs.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.geteventfiltertext">GetEventFilterText</a>
</td>
<td align="left" width="63%">
Returns a short description of an event for a specific filter.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getexceptionfilterparameters">GetExceptionFilterParameters</a>
</td>
<td align="left" width="63%">
Returns the parameters for exception filters specified by exception codes or by index.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getexceptionfiltersecondcommand">GetExceptionFilterSecondCommand</a>
</td>
<td align="left" width="63%">
Returns the command that will be executed by the debugger engine upon the second chance of a specified exception.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getexecutingprocessortype">GetExecutingProcessorType</a>
</td>
<td align="left" width="63%">
Returns the executing processor type for the processor for which the last event occurred.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getexecutionstatus">GetExecutionStatus</a>
</td>
<td align="left" width="63%">
Returns information about the execution status of the debugger engine.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getextensionbypath">GetExtensionByPath</a>
</td>
<td align="left" width="63%">
Returns the handle for an already loaded extension library.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getextensionfunction">GetExtensionFunction</a>
</td>
<td align="left" width="63%">
Returns a pointer to an extension function from an extension library.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getinterrupt">GetInterrupt</a>
</td>
<td align="left" width="63%">
Checks whether a user interrupt was issued.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getinterrupttimeout">GetInterruptTimeout</a>
</td>
<td align="left" width="63%">
Returns the number of seconds that the engine will wait when requesting a break into the debugger.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getlasteventinformation">GetLastEventInformation</a>
</td>
<td align="left" width="63%">
Returns information about the last event that occurred in a target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getlogfile">GetLogFile</a>
</td>
<td align="left" width="63%">
Returns the name of the currently open log file.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getlogmask">GetLogMask</a>
</td>
<td align="left" width="63%">
Returns the output mask for the currently open log file.

HRESULT



</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getnearinstruction">GetNearInstruction</a>
</td>
<td align="left" width="63%">
Returns the location of a processor instruction relative to a given location.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getnotifyeventhandle">GetNotifyEventHandle</a>
</td>
<td align="left" width="63%">
Receives the handle of the event that will be signaled after the next exception in a target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getnumberbreakpoints">GetNumberBreakpoints</a>
</td>
<td align="left" width="63%">
Returns the number of breakpoints for the current process.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getnumbereventfilters">GetNumberEventFilters</a>
</td>
<td align="left" width="63%">
Returns the number of event filters currently used by the engine.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getnumberpossibleexecutingprocessortypes">GetNumberPossibleExecutingProcessorTypes</a>
</td>
<td align="left" width="63%">
Returns the number of processor types that are supported by the computer running the current target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getnumberprocessors">GetNumberProcessors</a>
</td>
<td align="left" width="63%">
Returns the number of processors on the computer running the current target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getnumbersupportedprocessortypes">GetNumberSupportedProcessorTypes</a>
</td>
<td align="left" width="63%">
Returns the number of processor types supported by the engine.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getpagesize">GetPageSize</a>
</td>
<td align="left" width="63%">
Returns the page size for the effective processor mode.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getpossibleexecutingprocessortypes">GetPossibleExecutingProcessorTypes</a>
</td>
<td align="left" width="63%">
Returns the processor types that are supported by the computer running the current target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getprocessortypenames">GetProcessorTypeNames</a>
</td>
<td align="left" width="63%">
Returns the full name and abbreviated name of the specified processor type.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getprompttext">GetPromptText</a>
</td>
<td align="left" width="63%">
Returns the standard prompt text that will be prepended to the formatted output specified in the <b>OutputPrompt</b> and <b>OutputPromptVaList</b> methods.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getradix">GetRadix</a>
</td>
<td align="left" width="63%">
Returns the default radix (number base) used by the debugger engine when it evaluates and displays MASM expressions, and when it displays symbol information.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getreturnoffset">GetReturnOffset</a>
</td>
<td align="left" width="63%">
 Returns the return address for the current function.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getspecificfilterargument">GetSpecificFilterArgument</a>
</td>
<td align="left" width="63%">
Returns the value of filter argument for thespecific filters that have an argument.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getspecificfilterparameters">GetSpecificFilterParameters</a>
</td>
<td align="left" width="63%">
Returns the parameters for specific event filters.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getstacktrace">GetStackTrace</a>
</td>
<td align="left" width="63%">
Returns the frames at the top of the specified call stack.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getsupportedprocessortypes">GetSupportedProcessorTypes</a>
</td>
<td align="left" width="63%">
Returns the processor types supported by the debugger engine. 


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getsystemerrorcontrol">GetSystemErrorControl</a>
</td>
<td align="left" width="63%">
Returns the control values for handling system errors.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getsystemversion">GetSystemVersion</a>
</td>
<td align="left" width="63%">
Returns information that identifies the operating system on the computer that is running the current target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.gettextmacro">GetTextMacro</a>
</td>
<td align="left" width="63%">
Returns the value of a fixed-name alias.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetWindbgExtensionApis32</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.getwindbgextensionapis64">GetWindbgExtensionApis64</a>
</td>
<td align="left" width="63%">
returns a structure that facilitates using the WdbgExts API.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.input">Input</a>
</td>
<td align="left" width="63%">
Requests an input string from the debugger engine.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.ispointer64bit">IsPointer64Bit</a>
</td>
<td align="left" width="63%">
Determines if the effective processor uses 64-bit pointers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.openlogfile">OpenLogFile</a>
</td>
<td align="left" width="63%">
Opens a log file that will receive output from the client objects.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.output">Output</a>
</td>
<td align="left" width="63%">
Formats a string and sends the result to output callbacks that have been registered with the engine's clients.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.outputcurrentstate">OutputCurrentState</a>
</td>
<td align="left" width="63%">
Prints the current state of the current target to the debugger console.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.outputdisassembly">OutputDisassembly</a>
</td>
<td align="left" width="63%">
Disassembles a processor instruction and sends the disassembly to the output callbacks.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.outputdisassemblylines">OutputDisassemblyLines</a>
</td>
<td align="left" width="63%">
Disassembles several processor instructions and sends the resulting assembly instructions to the output callbacks.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.outputprompt">OutputPrompt</a>
</td>
<td align="left" width="63%">
 Formats and sends a user prompt to the output callback objects.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.outputpromptvalist">OutputPromptVaList</a>
</td>
<td align="left" width="63%">
Formats and sends a user prompt to the output callback objects.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.outputstacktrace">OutputStackTrace</a>
</td>
<td align="left" width="63%">
Outputs either the supplied stack frame or the current stack frames.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.outputvalist">OutputVaList</a>
</td>
<td align="left" width="63%">
 Formats a string and sends the result to the output callbacks that are registered with the engine's clients.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.outputversioninformation">OutputVersionInformation</a>
</td>
<td align="left" width="63%">
Prints version information about the debugger engine to the debugger console.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.readbugcheckdata">ReadBugCheckData</a>
</td>
<td align="left" width="63%">
Reads the kernel bug check code and related parameters.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.removebreakpoint">RemoveBreakpoint</a>
</td>
<td align="left" width="63%">
Removes a breakpoint.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.removeengineoptions">RemoveEngineOptions</a>
</td>
<td align="left" width="63%">
Turns off some of the engine's options.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.removeextension">RemoveExtension</a>
</td>
<td align="left" width="63%">
Unloads an extension library.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.returninput">ReturnInput</a>
</td>
<td align="left" width="63%">
This method is used by <a href="..\dbgeng\nn-dbgeng-idebuginputcallbacks.md">IDebugInputCallbacks</a> objects to send an input string to the engine following a request for input.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.setcodelevel">SetCodeLevel</a>
</td>
<td align="left" width="63%">
Sets the current code level and is mainly used when stepping through code.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.seteffectiveprocessortype">SetEffectiveProcessorType</a>
</td>
<td align="left" width="63%">
Sets the effective processor type of the processor of the computer that is running the target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.setengineoptions">SetEngineOptions</a>
</td>
<td align="left" width="63%">
Changes the engine's options.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.seteventfiltercommand">SetEventFilterCommand</a>
</td>
<td align="left" width="63%">
Sets a debugger command for the engine to execute when a specified event occurs.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.setexceptionfilterparameters">SetExceptionFilterParameters</a>
</td>
<td align="left" width="63%">
Changes the break status and handling status for some exception filters.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.setexceptionfiltersecondcommand">SetExceptionFilterSecondCommand</a>
</td>
<td align="left" width="63%">
Sets the command that will be executed by the debugger engine on the second chance of a specified exception.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.setexecutionstatus">SetExecutionStatus</a>
</td>
<td align="left" width="63%">
Requests that the debugger engine enter an executable state. Actual execution will not occur until the next time <b>WaitForEvent</b> is called.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.setinterrupt">SetInterrupt</a>
</td>
<td align="left" width="63%">
Registers a user interrupt or breaks into the debugger.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.setinterrupttimeout">SetInterruptTimeout</a>
</td>
<td align="left" width="63%">
Sets the number of seconds that the debugger engine should wait when requesting a break into the debugger.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.setlogmask">SetLogMask</a>
</td>
<td align="left" width="63%">
Sets the output mask for the currently open log file.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.setnotifyeventhandle">SetNotifyEventHandle</a>
</td>
<td align="left" width="63%">
Sets the event that will be signaled after the next exception in a target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.setradix">SetRadix</a>
</td>
<td align="left" width="63%">
Sets the default radix (number base) used by the debugger engine when it evaluates and displays MASM expressions, and when it displays symbol information.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.setspecificfilterargument">SetSpecificFilterArgument</a>
</td>
<td align="left" width="63%">
Sets the value of filter argument for the specific filters that can have an argument.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.setspecificfilterparameters">SetSpecificFilterParameters</a>
</td>
<td align="left" width="63%">
Changes the break status and handling status for some specific event filters.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.setsystemerrorcontrol">SetSystemErrorControl</a>
</td>
<td align="left" width="63%">
Sets the control values for handling system errors.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.settextmacro">SetTextMacro</a>
</td>
<td align="left" width="63%">
Sets the value of a fixed-name alias.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.waitforevent">WaitForEvent</a>
</td>
<td align="left" width="63%">
Waits for an event that breaks into the debugger engine application.


</td>
</tr>
</table>Creates a new breakpoint for the current target.


 Turns on some of the debugger engine's options.

Loads an extension library into the debugger engine.


Assembles a single processor instruction. The assembled instruction is placed in the target's memory.

Calls a debugger extension.

Closes the currently-open log file.

Converts a value of one type into a value of another type.


Converts an array of values into an array of values of different types.

Formats a string and sends the result to output callbacks that were registered with some of the engine's clients.


Formats a string and sends the result to output callbacks that were registered with some of the engine's clients.


Disassembles a processor instruction in the target's memory.


Evaluates an expression, returning the result.

Executes the specified debugger commands.


Opens the specified file and executes the debugger commands that are contained within.


Returns the processor type of the physical processor of the computer that is running the target.


Returns the breakpoint with the specified breakpoint ID.


Returns the breakpoint located at the specified index.


Returns the parameters of one or more breakpoints.


Returns the current code level and is mainly used when stepping through code.


Describes the nature of the current target.


Returns the address of the last instruction disassembled using Disassemble.


Returns the effective processor type of the processor of the computer that is running the target.


Returns the engine's options.

Returns the debugger command that the engine will execute when a specified event occurs.


Returns a short description of an event for a specific filter.


Returns the parameters for exception filters specified by exception codes or by index.


Returns the command that will be executed by the debugger engine upon the second chance of a specified exception.


Returns the executing processor type for the processor for which the last event occurred.


Returns information about the execution status of the debugger engine.


Returns the handle for an already loaded extension library.


Returns a pointer to an extension function from an extension library.


Checks whether a user interrupt was issued.

Returns the number of seconds that the engine will wait when requesting a break into the debugger.

Returns information about the last event that occurred in a target.


Returns the name of the currently open log file.

Returns the output mask for the currently open log file.

HRESULT



Returns the location of a processor instruction relative to a given location.


Receives the handle of the event that will be signaled after the next exception in a target.


Returns the number of breakpoints for the current process.


Returns the number of event filters currently used by the engine.


Returns the number of processor types that are supported by the computer running the current target.

Returns the number of processors on the computer running the current target.


Returns the number of processor types supported by the engine.


Returns the page size for the effective processor mode.

Returns the processor types that are supported by the computer running the current target.


Returns the full name and abbreviated name of the specified processor type.


Returns the standard prompt text that will be prepended to the formatted output specified in the <b>OutputPrompt</b> and <b>OutputPromptVaList</b> methods.

Returns the default radix (number base) used by the debugger engine when it evaluates and displays MASM expressions, and when it displays symbol information.

 Returns the return address for the current function.

Returns the value of filter argument for thespecific filters that have an argument.


Returns the parameters for specific event filters.


Returns the frames at the top of the specified call stack.

Returns the processor types supported by the debugger engine. 


Returns the control values for handling system errors.


Returns information that identifies the operating system on the computer that is running the current target.

Returns the value of a fixed-name alias.



returns a structure that facilitates using the WdbgExts API.


Requests an input string from the debugger engine.


Determines if the effective processor uses 64-bit pointers.

Opens a log file that will receive output from the client objects.

Formats a string and sends the result to output callbacks that have been registered with the engine's clients.

Prints the current state of the current target to the debugger console.


Disassembles a processor instruction and sends the disassembly to the output callbacks.


Disassembles several processor instructions and sends the resulting assembly instructions to the output callbacks.

 Formats and sends a user prompt to the output callback objects.


Formats and sends a user prompt to the output callback objects.


Outputs either the supplied stack frame or the current stack frames.


 Formats a string and sends the result to the output callbacks that are registered with the engine's clients.


Prints version information about the debugger engine to the debugger console.


Reads the kernel bug check code and related parameters.


Removes a breakpoint.


Turns off some of the engine's options.


Unloads an extension library.

This method is used by <a href="..\dbgeng\nn-dbgeng-idebuginputcallbacks.md">IDebugInputCallbacks</a> objects to send an input string to the engine following a request for input.


Sets the current code level and is mainly used when stepping through code.


Sets the effective processor type of the processor of the computer that is running the target.


Changes the engine's options.


Sets a debugger command for the engine to execute when a specified event occurs.


Changes the break status and handling status for some exception filters.


Sets the command that will be executed by the debugger engine on the second chance of a specified exception.

Requests that the debugger engine enter an executable state. Actual execution will not occur until the next time <b>WaitForEvent</b> is called.


Registers a user interrupt or breaks into the debugger.

Sets the number of seconds that the debugger engine should wait when requesting a break into the debugger.

Sets the output mask for the currently open log file.


Sets the event that will be signaled after the next exception in a target.


Sets the default radix (number base) used by the debugger engine when it evaluates and displays MASM expressions, and when it displays symbol information.

Sets the value of filter argument for the specific filters that can have an argument.


Changes the break status and handling status for some specific event filters.


Sets the control values for handling system errors.

Sets the value of a fixed-name alias.

Waits for an event that breaks into the debugger engine application.


 


## -remarks


## -requirements
<table>
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

## -see-also
<dl>
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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl interface%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

