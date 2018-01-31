---
UID : NS:dbgeng._DEBUG_LAST_EVENT_INFO_EXIT_THREAD
title : "_DEBUG_LAST_EVENT_INFO_EXIT_THREAD"
author : windows-driver-content
description : Describes the exit thread of the last event.
old-location : debugger\debug_last_event_info_exit_thread.htm
old-project : debugger
ms.assetid : 1C7E79F2-120A-424B-B4E3-EF202FA90C2A
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : PDEBUG_LAST_EVENT_INFO_EXIT_THREAD, DEBUG_LAST_EVENT_INFO_EXIT_THREAD, dbgeng/PDEBUG_LAST_EVENT_INFO_EXIT_THREAD, _DEBUG_LAST_EVENT_INFO_EXIT_THREAD, DEBUG_LAST_EVENT_INFO_EXIT_THREAD structure [Windows Debugging], debugger.debug_last_event_info_exit_thread, PDEBUG_LAST_EVENT_INFO_EXIT_THREAD structure pointer [Windows Debugging], *PDEBUG_LAST_EVENT_INFO_EXIT_THREAD, dbgeng/DEBUG_LAST_EVENT_INFO_EXIT_THREAD
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : dbgeng.h
req.include-header : DbgEng.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DEBUG_LAST_EVENT_INFO_EXIT_THREAD, *PDEBUG_LAST_EVENT_INFO_EXIT_THREAD
---

# _DEBUG_LAST_EVENT_INFO_EXIT_THREAD structure
Describes the exit thread of the last event.

## Syntax
````
typedef struct _DEBUG_LAST_EVENT_INFO_EXIT_THREAD {
  ULONG ExitCode;
} DEBUG_LAST_EVENT_INFO_EXIT_THREAD, *PDEBUG_LAST_EVENT_INFO_EXIT_THREAD;
````

## Members


`ExitCode`

The exit code of the thread.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include DbgEng.h) |