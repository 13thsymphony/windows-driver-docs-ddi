---
UID: NS.DBGENG._DEBUG_LAST_EVENT_INFO_EXCEPTION
title: _DEBUG_LAST_EVENT_INFO_EXCEPTION
author: windows-driver-content
description: Describes the exception of the last event.
old-location: debugger\debug_last_event_info_exception.htm
old-project: debugger
ms.assetid: FB4EBA71-5144-440A-AFD1-7460903C9189
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DEBUG_LAST_EVENT_INFO_EXCEPTION, *PDEBUG_LAST_EVENT_INFO_EXCEPTION, DEBUG_LAST_EVENT_INFO_EXCEPTION
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
req.alt-api: DEBUG_LAST_EVENT_INFO_EXCEPTION
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

# _DEBUG_LAST_EVENT_INFO_EXCEPTION structure



## -description
Describes the exception of the last event.


## -syntax

````
typedef struct _DEBUG_LAST_EVENT_INFO_EXCEPTION {
  EXCEPTION_RECORD64 ExceptionRecord;
  ULONG              FirstChance;
} DEBUG_LAST_EVENT_INFO_EXCEPTION, *PDEBUG_LAST_EVENT_INFO_EXCEPTION;
````


## -struct-fields

### -field ExceptionRecord

An exception record.

### -field FirstChance

A first chance value.

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