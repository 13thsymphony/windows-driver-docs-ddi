---
UID: NF:ksproxy.IKsClockPropertySet.KsGetPhysicalTime
title: IKsClockPropertySet::KsGetPhysicalTime method
author: windows-driver-content
description: The KsGetPhysicalTime method retrieves the physical time from the underlying clock.
old-location: stream\iksclockpropertyset_ksgetphysicaltime.htm
old-project: stream
ms.assetid: 25875f28-292f-40d9-8b29-ec9af49b0bc0
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsClockPropertySet, IKsClockPropertySet interface [Streaming Media Devices], KsGetPhysicalTime method, IKsClockPropertySet::KsGetPhysicalTime, KsGetPhysicalTime method [Streaming Media Devices], KsGetPhysicalTime method [Streaming Media Devices], IKsClockPropertySet interface, KsGetPhysicalTime,IKsClockPropertySet.KsGetPhysicalTime, ksproxy/IKsClockPropertySet::KsGetPhysicalTime, ksproxy_d242cd7a-c210-41b2-9c3c-59900c79e351.xml, stream.iksclockpropertyset_ksgetphysicaltime
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
-	IKsClockPropertySet.KsGetPhysicalTime
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---


# KsGetPhysicalTime method
The <b>KsGetPhysicalTime</b> method retrieves the physical time from the underlying clock.

## Syntax

````
HRESULT KsGetPhysicalTime(
  [out] LONGLONG *Time
);
````

## Parameters

`Time`

Pointer to a variable that receives the current physical time.


## Return Value

Returns NOERROR if successful; otherwise, returns an error code.

## Remarks

The physical time is based on some underlying physical clock that always progresses, even if the physical type of clock must be changed in real time. Other physical clocks use an underlying clock's physical time for rate matching.

The proxy uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565088">KSPROPERTY_CLOCK_PHYSICALTIME</a> property to retrieve the physical time.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ksproxy.h (include Ksproxy.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565088">KSPROPERTY_CLOCK_PHYSICALTIME</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559760">IKsClockPropertySet::KsSetPhysicalTime</a>