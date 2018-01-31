---
UID : NS:dbgeng._DEBUG_LAST_EVENT_INFO_EXIT_PROCESS
title : "_DEBUG_LAST_EVENT_INFO_EXIT_PROCESS"
author : windows-driver-content
description : Describes the exit process of the last event.
old-location : debugger\debug_last_event_info_exit_process.htm
old-project : debugger
ms.assetid : B4AFCD4C-0415-4EC4-BC10-D98F3AB409C5
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : "_DEBUG_LAST_EVENT_INFO_EXIT_PROCESS, dbgeng/PDEBUG_LAST_EVENT_INFO_EXIT_PROCESS, debugger.debug_last_event_info_exit_process, dbgeng/DEBUG_LAST_EVENT_INFO_EXIT_PROCESS, PDEBUG_LAST_EVENT_INFO_EXIT_PROCESS structure pointer [Windows Debugging], PDEBUG_LAST_EVENT_INFO_EXIT_PROCESS, DEBUG_LAST_EVENT_INFO_EXIT_PROCESS structure [Windows Debugging], *PDEBUG_LAST_EVENT_INFO_EXIT_PROCESS, DEBUG_LAST_EVENT_INFO_EXIT_PROCESS"
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
req.typenames : "*PDEBUG_LAST_EVENT_INFO_EXIT_PROCESS, DEBUG_LAST_EVENT_INFO_EXIT_PROCESS"
---

# _DEBUG_LAST_EVENT_INFO_EXIT_PROCESS structure
Describes the exit process of the last event.

## Syntax
````
typedef struct _DEBUG_LAST_EVENT_INFO_EXIT_PROCESS {
  ULONG ExitCode;
} DEBUG_LAST_EVENT_INFO_EXIT_PROCESS, *PDEBUG_LAST_EVENT_INFO_EXIT_PROCESS;
````

## Members


`ExitCode`

The exit code of the process.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include DbgEng.h) |