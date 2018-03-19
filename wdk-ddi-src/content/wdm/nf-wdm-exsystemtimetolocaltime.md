---
UID: NF:wdm.ExSystemTimeToLocalTime
title: ExSystemTimeToLocalTime function
author: windows-driver-content
description: The ExSystemTimeToLocalTime routine converts a GMT system time value to the local system time for the current time zone.
old-location: kernel\exsystemtimetolocaltime.htm
old-project: kernel
ms.assetid: d77ce60e-7b23-4f60-af63-d613ceba281e
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: ExSystemTimeToLocalTime, ExSystemTimeToLocalTime routine [Kernel-Mode Driver Architecture], k102_9cf20274-70ae-41f6-b56f-2dc8aa7fd0e3.xml, kernel.exsystemtimetolocaltime, wdm/ExSystemTimeToLocalTime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
-	ExSystemTimeToLocalTime
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ExSystemTimeToLocalTime function
The <b>ExSystemTimeToLocalTime</b> routine converts a GMT system time value to the local system time for the current time zone.

## Syntax

````
VOID ExSystemTimeToLocalTime(
  _In_  PLARGE_INTEGER SystemTime,
  _Out_ PLARGE_INTEGER LocalTime
);
````

## Parameters

`SystemTime`

A pointer to a variable set to the unbiased, GMT system time.

`LocalTime`

A pointer to the returned value for the current locale.


## Return Value

None

## Remarks

<b>ExSystemTimeToLocalTime</b> subtracts the time-zone bias from the GMT system time value to compute the corresponding time at the current locale.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="..\wdm\nf-wdm-exlocaltimetosystemtime.md">ExLocalTimeToSystemTime</a>