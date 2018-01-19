---
UID : NF:dbgeng.IDebugEventCallbacks.ExitProcess
title : IDebugEventCallbacks::ExitProcess method
author : windows-driver-content
description : The ExitProcess callback method is called by the engine when an exit-processdebugging event occurs in the target.
old-location : debugger\idebugeventcallbacks_exitprocess.htm
old-project : debugger
ms.assetid : 050b747e-5570-4e25-81e4-eccdde4f6995
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : IDebugEventCallbacks, IDebugEventCallbacks::ExitProcess, ExitProcess
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
req.alt-api : IDebugEventCallbacks.ExitProcess
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


# ExitProcess method
The <b>ExitProcess</b> callback method is called by the engine when an exit-processdebugging event occurs in the target.

## Syntax

````
HRESULT ExitProcess(
  [in] ULONG ExitCode
);
````

## Parameters

`ExitCode`

Specifies the exit code for the process.


## Return Value

This method returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.

## Remarks

This method is only called by the engine if the DEBUG_EVENT_EXIT_PROCESS flag is set in the mask returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550737">IDebugEventCallbacks::GetInterestMask</a>.

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.  For information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.</p>

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