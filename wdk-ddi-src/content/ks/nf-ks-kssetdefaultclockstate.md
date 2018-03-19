---
UID: NF:ks.KsSetDefaultClockState
title: KsSetDefaultClockState function
author: windows-driver-content
description: The KsSetDefaultClockState function sets the current state of the clock that is used to reflect the current state of the underlying filter pin.
old-location: stream\kssetdefaultclockstate.htm
old-project: stream
ms.assetid: 5893f4ff-0eb5-4cdc-8f58-f7654c1ce9fc
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsSetDefaultClockState, KsSetDefaultClockState function [Streaming Media Devices], ks/KsSetDefaultClockState, ksfunc_a57f26f0-cd4a-4d80-a090-788aef1ccf4b.xml, stream.kssetdefaultclockstate
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
-	KsSetDefaultClockState
product: Windows
targetos: Windows
req.typenames: 
---


# KsSetDefaultClockState function
The <b>KsSetDefaultClockState</b> function sets the current state of the clock that is used to reflect the current state of the underlying filter pin. The owner of the default clock is expected to serialize access to this function and to call <a href="..\ks\nf-ks-kssetdefaultclocktime.md">KsSetDefaultClockTime</a>.

The function can be called at DISPATCH_LEVEL.

## Syntax

````
VOID KsSetDefaultClockState(
  _In_ PKSDEFAULTCLOCK DefaultClock,
  _In_ KSSTATE         State
);
````

## Parameters

`DefaultClock`

Specifies an initialize default clock structure that is shared among any instance of the default clock for the parent.

`State`

Specifies the new state to set the clock.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |

## See Also

<a href="..\ks\nf-ks-ksgetdefaultclockstate.md">KsGetDefaultClockState</a>