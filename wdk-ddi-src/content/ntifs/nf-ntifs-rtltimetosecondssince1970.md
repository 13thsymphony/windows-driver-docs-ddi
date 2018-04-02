---
UID: NF:ntifs.RtlTimeToSecondsSince1970
title: RtlTimeToSecondsSince1970 function
author: windows-driver-content
description: The RtlTimeToSecondsSince1970 routine converts a given absolute system time value to the elapsed time, in seconds, since the beginning of 1970.
old-location: ifsk\rtltimetosecondssince1970.htm
old-project: ifsk
ms.assetid: 9f3e8592-b966-45c4-8931-dd5be0d75740
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RtlTimeToSecondsSince1970, RtlTimeToSecondsSince1970 routine [Installable File System Drivers], ifsk.rtltimetosecondssince1970, ntifs/RtlTimeToSecondsSince1970, rtlref_62b40f46-c3ee-480d-b671-0c107866f4e7.xml
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
-	RtlTimeToSecondsSince1970
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlTimeToSecondsSince1970 function
The <b>RtlTimeToSecondsSince1970</b> routine converts a given absolute system time value to the elapsed time, in seconds, since the beginning of 1970.

## Syntax

```
NTSYSAPI BOOLEAN RtlTimeToSecondsSince1970(
  PLARGE_INTEGER Time,
  PULONG         ElapsedSeconds
);
```

## Parameters

`Time`

Pointer to a variable that specifies the system time value to be converted. The approximate valid range for this variable begins at 1970 and ends around 2105.

`ElapsedSeconds`

Pointer to a caller-allocated variable that receives the corresponding number of seconds since midnight, December 31, 1969.


## Return Value

<b>RtlTimeToSecondsSince1970</b> returns <b>TRUE</b> if the input <i>Time</i> falls within a range that it can accurately convert to <i>ElapsedSeconds</i>.

## Remarks

The basis for system time is the start of 1601. The absolute system time is a LARGE_INTEGER value, accurate to 100-nanosecond resolution, assuming an accurate hardware clock. The value processed by <b>RtlTimeToSecondsSince1970</b> is truncated to one-millisecond resolution. 

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