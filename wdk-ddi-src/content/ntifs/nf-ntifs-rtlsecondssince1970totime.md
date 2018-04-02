---
UID: NF:ntifs.RtlSecondsSince1970ToTime
title: RtlSecondsSince1970ToTime function
author: windows-driver-content
description: The RtlSecondsSince1970ToTime routine converts the elapsed time, in seconds, since the beginning of 1970 to an absolute system time value.
old-location: ifsk\rtlsecondssince1970totime.htm
old-project: ifsk
ms.assetid: 8ec961c6-235c-4980-ac4c-60aa496e8a5d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RtlSecondsSince1970ToTime, RtlSecondsSince1970ToTime routine [Installable File System Drivers], ifsk.rtlsecondssince1970totime, ntifs/RtlSecondsSince1970ToTime, rtlref_ca1b3241-af9f-48e1-86e0-56f94c459c63.xml
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
-	RtlSecondsSince1970ToTime
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlSecondsSince1970ToTime function
The <b>RtlSecondsSince1970ToTime</b> routine converts the elapsed time, in seconds, since the beginning of 1970 to an absolute system time value.

## Syntax

```
NTSYSAPI VOID RtlSecondsSince1970ToTime(
  ULONG          ElapsedSeconds,
  PLARGE_INTEGER Time
);
```

## Parameters

`ElapsedSeconds`

Number of seconds from midnight, December 31, 1969, to the current date and time.

`Time`

Pointer to a caller-allocated variable that receives the corresponding current system time.


## Return Value

None

## Remarks

The basis for system time is the start of 1601. The absolute system time is a LARGE_INTEGER value, accurate to 100-nanosecond resolution, assuming an accurate hardware clock. The value returned by <b>RtlSecondsSince1970ToTime</b> is truncated to one-millisecond resolution. 

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553210">RtlSecondsSince1980ToTime</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562879">RtlTimeFieldsToTime</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553241">RtlTimeToSecondsSince1970</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562884">RtlTimeToTimeFields</a>