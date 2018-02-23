---
UID: NF:dbgeng.IDebugEventCallbacksWide.ExitThread
title: IDebugEventCallbacksWide::ExitThread method
author: windows-driver-content
description: The ExitThread callback method is called by the engine when an exit-threaddebugging event occurs in the target.
old-location: debugger\idebugeventcallbackswide_exitthread.htm
old-project: Debugger
ms.assetid: 77933fa9-ff30-45cf-894d-83a425802e25
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugEventCallbacksWide, ExitThread method [Windows Debugging], IDebugEventCallbacksWide interface, debugger.idebugeventcallbackswide_exitthread, ExitThread method [Windows Debugging], IDebugEventCallbacksWide::ExitThread, IDebugEventCallbacksWide interface [Windows Debugging], ExitThread method, dbgeng/IDebugEventCallbacksWide::ExitThread, ExitThread
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
-	IDebugEventCallbacksWide.ExitThread
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# ExitThread method
The <b>ExitThread</b> callback method is called by the engine when an exit-threaddebugging event occurs in the target.

## Syntax

````
HRESULT ExitThread(
  [in] ULONG ExitCode
);
````

## Parameters

`ExitCode`

Specifies the exit code for the thread.


## Return Value

This method returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.

## Remarks

This method is only called by the engine if the DEBUG_EVENT_EXIT_THREAD flag is set in the mask returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550625">IDebugEventCallbacksWide::GetInterestMask</a>.

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.  For information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |