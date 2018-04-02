---
UID: NF:ks.IKsReferenceClock.GetState
title: IKsReferenceClock::GetState method
author: windows-driver-content
description: The IKsReferenceClock::GetState method queries the associated reference clock for its current streaming state.
old-location: stream\iksreferenceclock_getstate.htm
old-project: stream
ms.assetid: 5a77a8bc-b477-41b3-bc4e-07c6c14291a1
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetState method [Streaming Media Devices], GetState method [Streaming Media Devices], IKsReferenceClock interface, GetState,IKsReferenceClock.GetState, IKsReferenceClock, IKsReferenceClock interface [Streaming Media Devices], GetState method, IKsReferenceClock::GetState, avintfc_e2017894-2e83-4091-84b7-5ea793076b29.xml, ks/IKsReferenceClock::GetState, stream.iksreferenceclock_getstate
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
-	IKsReferenceClock.GetState
product: Windows
targetos: Windows
req.typenames: 
---


# IKsReferenceClock::GetState method
The <b>IKsReferenceClock::GetState</b> method queries the associated reference clock for its current streaming state.

## Syntax

```
NTSTATUS GetState(
  PKSSTATE State
);
```

## Parameters

`State`

Points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566856">KSSTATE</a> structure that indicates the streaming state of the underlying clock.


## Return Value

The <b>IKsReferenceClock::GetState</b> method returns STATUS_SUCCESS or  the error code that the relevant clock returned from its <b>GetState</b> property. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff565093">KSPROPERTY_CLOCK_STATE</a>.  May return STATUS_DEVICE_NOT_READY if no clock is assigned.

## Remarks

For more information, see <a href="https://msdn.microsoft.com/fc1d5bca-72e3-48e2-b46f-09a13bba83b4">AVStream Clocks</a>.

AVStream uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565093">KSPROPERTY_CLOCK_STATE</a> property to retrieve the correlated time.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566856">KSSTATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563517">KsPinGetReferenceClockInterface</a>