---
UID: NF:ks.IKsReferenceClock.GetCorrelatedTime
title: IKsReferenceClock::GetCorrelatedTime method
author: windows-driver-content
description: The IKsReferenceClock::GetCorrelatedTime method queries the associated reference clock for current stream time and acquires the correlated system time.
old-location: stream\iksreferenceclock_getcorrelatedtime.htm
old-project: stream
ms.assetid: 3f4a47bb-460e-4ca0-9aee-4bcfdb88dd30
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetCorrelatedTime method [Streaming Media Devices], GetCorrelatedTime method [Streaming Media Devices], IKsReferenceClock interface, GetCorrelatedTime,IKsReferenceClock.GetCorrelatedTime, IKsReferenceClock, IKsReferenceClock interface [Streaming Media Devices], GetCorrelatedTime method, IKsReferenceClock::GetCorrelatedTime, avintfc_9bb8180e-a8e6-4b89-a615-0516470a7dd8.xml, ks/IKsReferenceClock::GetCorrelatedTime, stream.iksreferenceclock_getcorrelatedtime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ks.h
req.include-header: Ks.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ks.h
api_name:
-	IKsReferenceClock.GetCorrelatedTime
product: Windows
targetos: Windows
req.typenames: 
---


# GetCorrelatedTime method
The <b>IKsReferenceClock::GetCorrelatedTime</b> method queries the associated reference clock for current stream time and acquires the correlated system time.

## Syntax

````
LONGLONG GetCorrelatedTime(
  [out] PLONGLONG SystemTime
);
````

## Parameters

`SystemTime`

A pointer to a LONGLONG-typed variable that receives the current system time in 100 nanosecond units.


## Return Value

The <b>IKsReferenceClock::GetCorrelatedTime</b> method returns the stream time, specified by default in 100-nanosecond units. The correlated system time is returned in <i>SystemTime</i>.

## Remarks

Use this method to determine the difference between stream time and system time. <b>IKsReferenceClock::GetCorrelatedTime</b> returns the times that both clocks show at the same moment.

For the most accurate results, call this method only when the stream is in a running state (KSSTATE_RUN) and not during a state transition.

You should use this method when obtaining a time stamp to put in the <b>PresentationTime</b> member of <a href="..\ks\ns-ks-ksstream_header.md">KSSTREAM_HEADER</a>.

For more information, see <a href="https://msdn.microsoft.com/fc1d5bca-72e3-48e2-b46f-09a13bba83b4">AVStream Clocks</a>.

AVStream uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564465">KSPROPERTY_CLOCK_CORRELATEDTIME</a> property to retrieve the correlated time.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="..\ks\nf-ks-kspingetreferenceclockinterface.md">KsPinGetReferenceClockInterface</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsReferenceClock::GetCorrelatedTime method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>