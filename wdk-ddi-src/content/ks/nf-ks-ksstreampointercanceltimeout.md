---
UID: NF:ks.KsStreamPointerCancelTimeout
title: KsStreamPointerCancelTimeout function
author: windows-driver-content
description: The KsStreamPointerCancelTimeout function cancels a previously scheduled time-out callback on the specified stream pointer.
old-location: stream\ksstreampointercanceltimeout.htm
old-project: stream
ms.assetid: 9e1dd010-0074-45fb-b3cb-f8ea7ad15e02
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsStreamPointerCancelTimeout, KsStreamPointerCancelTimeout function [Streaming Media Devices], avfunc_9496b7be-f178-418a-87ac-d09dec988672.xml, ks/KsStreamPointerCancelTimeout, stream.ksstreampointercanceltimeout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsStreamPointerCancelTimeout
product:
- Windows
targetos: Windows
req.typenames: 
---


# KsStreamPointerCancelTimeout function
The<b> KsStreamPointerCancelTimeout </b>function cancels a previously scheduled time-out callback on the specified stream pointer.

## Syntax

```
void KsStreamPointerCancelTimeout(
  PKSSTREAM_POINTER StreamPointer
);
```

## Parameters

`StreamPointer`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567139">KSSTREAM_POINTER</a> structure representing the stream pointer for which to cancel a registered time-out callback.


## Return Value

None

## Remarks

Minidrivers should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff567135">KsStreamPointerScheduleTimeout</a> to schedule a time-out callback on a specified stream pointer.

The <b>KsStreamPointerCancelTimeout</b> function does not affect stream pointers that have no currently scheduled time-out callback.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563512">KsPinGetFirstCloneStreamPointer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567135">KsStreamPointerScheduleTimeout</a>