---
UID: NC:ks.PFNKSCLOCK_CORRELATEDTIME
title: PFNKSCLOCK_CORRELATEDTIME
author: windows-driver-content
description: The routine is a system-supplied routine that retrieves and the following:KStrClockGetCorrelatedTime is a system-supplied routine that retrieves both the current system time and the corresponding clock tick count since boot.KStrClockGetCorrelatedPhysicalTime is a system-supplied routine that retrieves both the current system time minus suspended delta and the corresponding clock tick since boot.
old-location: stream\kstrclockgetcorrelatedtime.htm
old-project: stream
ms.assetid: 1fc71718-a1fb-4e82-9805-7830e761cd6d
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KStrClockGetCorrelatedPhysicalTime, KStrClockGetCorrelatedTime, PFNKSCLOCK_CORRELATEDTIME, SystemCorrelatedTime, SystemCorrelatedTime routine [Streaming Media Devices], ks/SystemCorrelatedTime, ksfunc_dd229adf-e2be-44ac-bda2-f947b0f559a3.xml, stream.kstrclockgetcorrelatedtime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ks.h
api_name:
-	SystemCorrelatedTime
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---


# PFNKSCLOCK_CORRELATEDTIME callback function
The routine 
      is a system-supplied routine that retrieves  and the following:

<i>KStrClockGetCorrelatedTime</i> is a system-supplied routine that retrieves both the current system time and the corresponding clock tick count since boot.

<i>KStrClockGetCorrelatedPhysicalTime</i> is a system-supplied routine that retrieves both the current system time minus suspended delta and the corresponding clock tick since boot.

## Syntax

```
PFNKSCLOCK_CORRELATEDTIME PfnksclockCorrelatedtime;

LONGLONG PfnksclockCorrelatedtime(
  PFILE_OBJECT FileObject,
  PLONGLONG SystemTime
)
{...}
```

## Parameters

`FileObject`

A pointer to the <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a> structure to which a handle was returned when the clock instance was created.

`SystemTime`

A pointer to a 64-bit integer containing the number of clock ticks since system boot.


## Return Value

This routine returns the current system time as a value of type LONGLONG. This value is specified in 100 nanosecond units.

## Remarks

You can obtain an entry point for this routine by supplying a driver-allocated <a href="..\ks\ns-ks-ksclock_functiontable.md">KSCLOCK_FUNCTIONTABLE</a> structure in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564466">KSPROPERTY_CLOCK_FUNCTIONTABLE</a> request.

The system time is acquired from <a href="..\wdm\nf-wdm-kequeryperformancecounter.md">KeQueryPerformanceCounter</a>.

Both time values are specified in 100 nanosecond units.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="..\ks\ns-ks-kscorrelated_time.md">KSCORRELATED_TIME</a>



<a href="..\ks\ns-ks-ksclock_functiontable.md">KSCLOCK_FUNCTIONTABLE</a>



<a href="..\wdm\nf-wdm-kequeryperformancecounter.md">KeQueryPerformanceCounter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564466">KSPROPERTY_CLOCK_FUNCTIONTABLE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSCLOCK_CORRELATEDTIME routine%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>