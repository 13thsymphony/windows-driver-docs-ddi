---
UID: NF:dbgeng.IDebugEventCallbacksWide.ExitProcess
title: IDebugEventCallbacksWide::ExitProcess method
author: windows-driver-content
description: The ExitProcess callback method is called by the engine when an exit-processdebugging event occurs in the target.
old-location: debugger\idebugeventcallbackswide_exitprocess.htm
old-project: debugger
ms.assetid: bc104b84-4f0a-420d-8c2c-14b33cc6ca04
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugEventCallbacksWide::ExitProcess, ExitProcess, ExitProcess method [Windows Debugging], debugger.idebugeventcallbackswide_exitprocess, IDebugEventCallbacksWide interface [Windows Debugging], ExitProcess method, ExitProcess method [Windows Debugging], IDebugEventCallbacksWide interface, IDebugEventCallbacksWide, dbgeng/IDebugEventCallbacksWide::ExitProcess
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugEventCallbacksWide.ExitProcess
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
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

This method is only called by the engine if the DEBUG_EVENT_EXIT_PROCESS flag is set in the mask returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550625">IDebugEventCallbacksWide::GetInterestMask</a>.

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.  For information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |