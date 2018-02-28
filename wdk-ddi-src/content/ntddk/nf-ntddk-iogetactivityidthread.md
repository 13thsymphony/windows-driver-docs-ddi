---
UID: NF:ntddk.IoGetActivityIdThread
title: IoGetActivityIdThread function
author: windows-driver-content
description: The IoGetActivityIdThread routine returns the activity ID associated with the current thread.
old-location: kernel\iogetactivityidthread.htm
old-project: kernel
ms.assetid: 445A9EBA-EF15-4FE4-9747-3E1E138E13E7
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IoGetActivityIdThread, IoGetActivityIdThread routine [Kernel-Mode Driver Architecture], kernel.iogetactivityidthread, ntddk/IoGetActivityIdThread
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 8.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoGetActivityIdThread
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# IoGetActivityIdThread function
The IoGetActivityIdThread routine returns the activity ID associated with the current thread.

## Syntax

````
LPCGUID IoGetActivityIdThread(
    None.
);
````

## Parameters

This function has no parameters.

## Return Value

The activity ID associated with the current thread.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with  Windows 8.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |