---
UID : NF:ks.IKsReferenceClock.GetTime
title : IKsReferenceClock::GetTime method
author : windows-driver-content
description : The IKsReferenceClock::GetTime method queries the associated reference clock for the current time.
old-location : stream\iksreferenceclock_gettime.htm
old-project : stream
ms.assetid : 3e5ff621-47ec-4ab7-bf8e-26bff57588f8
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : IKsReferenceClock, IKsReferenceClock::GetTime, GetTime
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : ks.h
req.include-header : Ks.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IKsReferenceClock.GetTime
req.alt-loc : ks.h
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
req.typenames : 
---


# GetTime method
The <b>IKsReferenceClock::GetTime</b> method queries the associated reference clock for the current time.

## Syntax

````
LONGLONG GetTime();
````

## Parameters

This function has no parameters.

## Return Value

The <b>IKsReferenceClock::GetTime</b> method returns the current stream time for the associated pin, specified by default in 100-nanosecond units.

The <b>IKsReferenceClock::GetTime</b> method returns the current stream time for the associated pin, specified by default in 100-nanosecond units.

The <b>IKsReferenceClock::GetTime</b> method returns the current stream time for the associated pin, specified by default in 100-nanosecond units.

## Remarks

Do not call this method when obtaining a time stamp for the <b>PresentationTime</b> member of <a href="..\ks\ns-ks-ksstream_header.md">KSSTREAM_HEADER</a>. Instead, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff560728">IKsReferenceClock::GetCorrelatedTime</a> in this situation.

For more information, see <a href="https://msdn.microsoft.com/fc1d5bca-72e3-48e2-b46f-09a13bba83b4">AVStream Clocks</a>.

AVStream uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565095">KSPROPERTY_CLOCK_TIME</a> property to retrieve the current clock time.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ks\nf-ks-kspingetreferenceclockinterface.md">KsPinGetReferenceClockInterface</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsReferenceClock::GetTime method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>