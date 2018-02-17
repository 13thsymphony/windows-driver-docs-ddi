---
UID: NF:ntifs.RtlSecondsSince1980ToTime
title: RtlSecondsSince1980ToTime function
author: windows-driver-content
description: The RtlSecondsSince1980ToTime routine converts the elapsed time, in seconds, since the beginning of 1980 to an absolute system time value.
old-location: ifsk\rtlsecondssince1980totime.htm
old-project: ifsk
ms.assetid: 2552df19-424e-43ba-9c8d-431123353d4a
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: RtlSecondsSince1980ToTime routine [Installable File System Drivers], RtlSecondsSince1980ToTime, ifsk.rtlsecondssince1980totime, ntifs/RtlSecondsSince1980ToTime, rtlref_1896255f-11a2-445f-999a-95da533908d8.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlSecondsSince1980ToTime
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlSecondsSince1980ToTime function
The <b>RtlSecondsSince1980ToTime</b> routine converts the elapsed time, in seconds, since the beginning of 1980 to an absolute system time value.

## Syntax

````
VOID RtlSecondsSince1980ToTime(
  _In_  ULONG          ElapsedSeconds,
  _Out_ PLARGE_INTEGER Time
);
````

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

<a href="..\ntifs\nf-ntifs-rtltimetosecondssince1980.md">RtlTimeToSecondsSince1980</a>



<a href="..\wdm\nf-wdm-rtltimefieldstotime.md">RtlTimeFieldsToTime</a>



<a href="..\wdm\nf-wdm-rtltimetotimefields.md">RtlTimeToTimeFields</a>



<a href="..\ntifs\nf-ntifs-rtlsecondssince1970totime.md">RtlSecondsSince1970ToTime</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlSecondsSince1980ToTime routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>