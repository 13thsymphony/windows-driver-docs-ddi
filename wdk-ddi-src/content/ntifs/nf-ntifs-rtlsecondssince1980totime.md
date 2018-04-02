---
UID: NF:ntifs.RtlSecondsSince1980ToTime
title: RtlSecondsSince1980ToTime function
author: windows-driver-content
description: The RtlSecondsSince1980ToTime routine converts the elapsed time, in seconds, since the beginning of 1980 to an absolute system time value.
old-location: ifsk\rtlsecondssince1980totime.htm
old-project: ifsk
ms.assetid: 2552df19-424e-43ba-9c8d-431123353d4a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RtlSecondsSince1980ToTime, RtlSecondsSince1980ToTime routine [Installable File System Drivers], ifsk.rtlsecondssince1980totime, ntifs/RtlSecondsSince1980ToTime, rtlref_1896255f-11a2-445f-999a-95da533908d8.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlSecondsSince1980ToTime
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlSecondsSince1980ToTime function
The <b>RtlSecondsSince1980ToTime</b> routine converts the elapsed time, in seconds, since the beginning of 1980 to an absolute system time value.

## Syntax

```
NTSYSAPI VOID RtlSecondsSince1980ToTime(
  ULONG          ElapsedSeconds,
  PLARGE_INTEGER Time
);
```

## Parameters

`ElapsedSeconds`

Number of seconds from midnight, December 31, 1979, to the current date and time.

`Time`

Pointer to a caller-allocated variable that receives the corresponding current system time.


## Return Value

None

## Remarks

The absolute system time is a LARGE_INTEGER value, accurate to 100-nanosecond resolution, assuming an accurate hardware clock. The basis for system time is the start of 1601. The value returned by <b>RtlSecondsSince1980ToTime</b> is truncated to one-millisecond resolution. 

For more information about converting time values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542994">Data Conversions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "< DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553204">RtlSecondsSince1970ToTime</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562879">RtlTimeFieldsToTime</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553244">RtlTimeToSecondsSince1980</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562884">RtlTimeToTimeFields</a>