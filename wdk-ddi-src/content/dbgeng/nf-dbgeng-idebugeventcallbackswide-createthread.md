---
UID: NF:dbgeng.IDebugEventCallbacksWide.CreateThread
title: IDebugEventCallbacksWide::CreateThread method
author: windows-driver-content
description: The CreateThread callback method is called by the engine when a create-threaddebugging event occurs in the target.
old-location: debugger\idebugeventcallbackswide_createthread.htm
old-project: Debugger
ms.assetid: d845777c-1bc9-4ab3-9bfc-211f2231971e
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugEventCallbacksWide interface [Windows Debugging], CreateThread method, CreateThread method [Windows Debugging], IDebugEventCallbacksWide, CreateThread, dbgeng/IDebugEventCallbacksWide::CreateThread, debugger.idebugeventcallbackswide_createthread, IDebugEventCallbacksWide::CreateThread, CreateThread method [Windows Debugging], IDebugEventCallbacksWide interface
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
-	IDebugEventCallbacksWide.CreateThread
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# CreateThread method
The <b>CreateThread</b> callback method is called by the engine when a create-threaddebugging event occurs in the target.

## Syntax

````
HRESULT CreateThread(
  [in] ULONG64 Handle,
  [in] ULONG64 DataOffset,
  [in] ULONG64 StartOffset
);
````

## Parameters

`Handle`

Specifies the handle for the thread whose creation caused the event.  If this information is not available, <i>Handle</i> will be <b>NULL</b>.

`DataOffset`

Specifies a block of data that the operating system maintains for this thread. The actual data in the block is operating system-specific.  If the operating system does not have such a block, <i>DataOffset</i> will be <b>NULL</b>.

`StartOffset`

Specifies the starting location in the target's virtual address space of the thread.  If this information is not available, <i>StartOffset</i> will be <b>NULL</b>.


## Return Value

This method returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.

## Remarks

This method is only called by the engine if the DEBUG_EVENT_CREATE_THREAD flag is set in the mask returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550625">IDebugEventCallbacksWide::GetInterestMask</a>.

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.  For information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |