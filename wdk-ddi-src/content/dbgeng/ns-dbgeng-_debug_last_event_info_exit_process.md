---
UID: NS.DBGENG._DEBUG_LAST_EVENT_INFO_EXIT_PROCESS
title: _DEBUG_LAST_EVENT_INFO_EXIT_PROCESS
author: windows-driver-content
description: Describes the exit process of the last event.
old-location: debugger\debug_last_event_info_exit_process.htm
old-project: debugger
ms.assetid: B4AFCD4C-0415-4EC4-BC10-D98F3AB409C5
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DEBUG_LAST_EVENT_INFO_EXIT_PROCESS, *PDEBUG_LAST_EVENT_INFO_EXIT_PROCESS, DEBUG_LAST_EVENT_INFO_EXIT_PROCESS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dbgeng.h
req.include-header: DbgEng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DEBUG_LAST_EVENT_INFO_EXIT_PROCESS
req.alt-loc: DbgEng.h
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

# _DEBUG_LAST_EVENT_INFO_EXIT_PROCESS structure



## -description
Describes the exit process of the last event.


## -syntax

````
typedef struct _DEBUG_LAST_EVENT_INFO_EXIT_PROCESS {
  ULONG ExitCode;
} DEBUG_LAST_EVENT_INFO_EXIT_PROCESS, *PDEBUG_LAST_EVENT_INFO_EXIT_PROCESS;
````


## -struct-fields

### -field ExitCode

The exit code of the process.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>DbgEng.h (include DbgEng.h)</dt>
</dl>
</td>
</tr>
</table>