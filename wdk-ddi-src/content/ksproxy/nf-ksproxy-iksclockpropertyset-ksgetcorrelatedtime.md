---
UID: NF:ksproxy.IKsClockPropertySet.KsGetCorrelatedTime
title: IKsClockPropertySet::KsGetCorrelatedTime method
author: windows-driver-content
description: The KsGetCorrelatedTime method retrieves the current time and the correlated system time from the underlying clock.
old-location: stream\iksclockpropertyset_ksgetcorrelatedtime.htm
old-project: stream
ms.assetid: b91f33b3-2706-4c94-9960-ceea023891af
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsClockPropertySet, IKsClockPropertySet interface [Streaming Media Devices], KsGetCorrelatedTime method, IKsClockPropertySet::KsGetCorrelatedTime, KsGetCorrelatedTime method [Streaming Media Devices], KsGetCorrelatedTime method [Streaming Media Devices], IKsClockPropertySet interface, KsGetCorrelatedTime,IKsClockPropertySet.KsGetCorrelatedTime, ksproxy/IKsClockPropertySet::KsGetCorrelatedTime, ksproxy_79582c7f-456c-420e-88eb-b0cb6916040f.xml, stream.iksclockpropertyset_ksgetcorrelatedtime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h
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
-	COM
api_location:
-	ksproxy.h
api_name:
-	IKsClockPropertySet.KsGetCorrelatedTime
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---


# KsGetCorrelatedTime method
The <b>KsGetCorrelatedTime</b> method retrieves the current time and the correlated system time from the underlying clock.

## Syntax

````
HRESULT KsGetCorrelatedTime(
  [out] KSCORRELATED_TIME *CorrelatedTime
);
````

## Parameters

`CorrelatedTime`

Pointer to a variable that receives a <a href="..\ks\ns-ks-kscorrelated_time.md">KSCORRELATED_TIME</a> structure that contains the current clock time along with the correlated system time.


## Return Value

Returns NOERROR if successful; otherwise, returns an error code.

## Remarks

The <b>KsGetCorrelatedTime</b> method retrieves the current time and the correlated system in an atomic operation. 

The proxy uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564465">KSPROPERTY_CLOCK_CORRELATEDTIME</a> property to retrieve the correlated time.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ksproxy.h (include Ksproxy.h) |

## See Also

<a href="..\ks\ns-ks-kscorrelated_time.md">KSCORRELATED_TIME</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564465">KSPROPERTY_CLOCK_CORRELATEDTIME</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559756">IKsClockPropertySet::KsSetCorrelatedTime</a>