---
UID : NF:ntddk.IoSetActivityIdThread
title : IoSetActivityIdThread function
author : windows-driver-content
description : The IoSetActivityIdThread routine associates an activity ID with the current thread. Drivers should use this routine when they are tracing aware and are issuing I/O on a worker thread.
old-location : kernel\iosetactivityidthread.htm
old-project : kernel
ms.assetid : 4C7884AB-C763-4FAF-8799-E0113B3F3AE0
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : IoSetActivityIdThread routine [Kernel-Mode Driver Architecture], IoSetActivityIdThread, ntddk/IoSetActivityIdThread, kernel.iosetactivityidthread
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntddk.h
req.include-header : Ntddk.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with  Windows 8.
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
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : Any level
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# IoSetActivityIdThread function
The IoSetActivityIdThread routine associates an activity ID with the current thread. Drivers should use this routine when they are tracing aware and are issuing I/O on a worker thread.

## Syntax

````
LPGUID IoSetActivityIdThread(
   LPGUID ActivityId
);
````

## Parameters

`ActivityId`

The activity ID provided by caller.


## Return Value

The activity ID that was previously set on the thread. Drivers must call IoClearActivityIdThread with this pointer when tracing is completed within the same thread context.

## Remarks

Drivers that use  I/O work items do not need to call this routine because the I/O subsystem takes care of propagating activity IDs to threads in that case.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** |  |