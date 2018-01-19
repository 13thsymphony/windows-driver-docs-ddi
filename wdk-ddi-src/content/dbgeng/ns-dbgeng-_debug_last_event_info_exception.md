---
UID : NS:dbgeng._DEBUG_LAST_EVENT_INFO_EXCEPTION
title : _DEBUG_LAST_EVENT_INFO_EXCEPTION
author : windows-driver-content
description : Describes the exception of the last event.
old-location : debugger\debug_last_event_info_exception.htm
old-project : debugger
ms.assetid : FB4EBA71-5144-440A-AFD1-7460903C9189
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _DEBUG_LAST_EVENT_INFO_EXCEPTION, DEBUG_LAST_EVENT_INFO_EXCEPTION, *PDEBUG_LAST_EVENT_INFO_EXCEPTION
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
req.alt-api : DEBUG_LAST_EVENT_INFO_EXCEPTION
req.alt-loc : DbgEng.h
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
req.typenames : DEBUG_LAST_EVENT_INFO_EXCEPTION, *PDEBUG_LAST_EVENT_INFO_EXCEPTION
---

# _DEBUG_LAST_EVENT_INFO_EXCEPTION structure
Describes the exception of the last event.

## Syntax
````
typedef struct _DEBUG_LAST_EVENT_INFO_EXCEPTION {
  EXCEPTION_RECORD64 ExceptionRecord;
  ULONG              FirstChance;
} DEBUG_LAST_EVENT_INFO_EXCEPTION, *PDEBUG_LAST_EVENT_INFO_EXCEPTION;
````

## Members

        
            `ExceptionRecord`

            An exception record.
        
            `FirstChance`

            A first chance value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include DbgEng.h) |