---
UID: NF:ks.KsSetDefaultClockTime
title: KsSetDefaultClockTime function
author: windows-driver-content
description: The KsSetDefaultClockTime function sets the current time of the clock.
old-location: stream\kssetdefaultclocktime.htm
old-project: stream
ms.assetid: c8b4fef4-cfbb-4cdd-b762-062b8ae4a423
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsSetDefaultClockTime, KsSetDefaultClockTime function [Streaming Media Devices], ks/KsSetDefaultClockTime, ksfunc_737648d0-8fc4-405c-96c8-61778e6758e9.xml, stream.kssetdefaultclocktime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsSetDefaultClockTime
product: Windows
targetos: Windows
req.typenames: 
---


# KsSetDefaultClockTime function
The <b>KsSetDefaultClockTime</b> function sets the current time of the clock. It modifies the current time returned by the clock. The owner of the default clock is expected to serialize access to this function and to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566820">KsSetDefaultClockState</a> function.

The function can be called at DISPATCH_LEVEL.

## Syntax

```
KSDDKAPI VOID KsSetDefaultClockTime(
  PKSDEFAULTCLOCK DefaultClock,
  LONGLONG        Time
);
```

## Parameters

`DefaultClock`

Specifies an initialize default clock structure that is shared among instances of the default clock for the parent.

`Time`

Specifies the new time to set the clock.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562614">KsGetDefaultClockTime</a>