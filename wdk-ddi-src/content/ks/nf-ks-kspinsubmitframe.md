---
UID: NF:ks.KsPinSubmitFrame
title: KsPinSubmitFrame function
author: windows-driver-content
description: If a pin has been placed into injection mode by a call to KsPinRegisterFrameReturnCallback, the KsPinSubmitFrame function submits a frame directly into the transport circuit.
old-location: stream\kspinsubmitframe.htm
old-project: stream
ms.assetid: 3fdb83b2-85b7-4f86-9a59-a42138000214
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsPinSubmitFrame, KsPinSubmitFrame function [Streaming Media Devices], avfunc_ce7c4c71-c404-4061-a2e5-b9f4c15df4a2.xml, ks/KsPinSubmitFrame, stream.kspinsubmitframe
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
-	KsPinSubmitFrame
product: Windows
targetos: Windows
req.typenames: 
---


# KsPinSubmitFrame function
If a pin has been placed into injection mode by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff563522">KsPinRegisterFrameReturnCallback</a>, the <b>KsPinSubmitFrame</b> function submits a frame directly into the transport circuit.

## Syntax

```
KSDDKAPI NTSTATUS KsPinSubmitFrame(
  PKSPIN           Pin,
  PVOID            Data,
  ULONG Size       OPTIONAL,
  PKSSTREAM_HEADER StreamHeader,
  PVOID            Context
);
```

## Parameters

`Pin`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure on which to submit a frame.

`Data`

A pointer to a frame buffer. This should be <b>NULL</b> if and only if <i>Size</i> is equal to 0. Optional.

`OPTIONAL`

TBD

`StreamHeader`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567138">KSSTREAM_HEADER</a> structure. The stream header is copied if this parameter is supplied. Optional.

`Context`

A pointer to a caller-allocated buffer. AVStream provides this pointer to the frame return callback registered through a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff563522">KsPinRegisterFrameReturnCallback</a>. Optional.


## Return Value

Returns STATUS_SUCCESS if frame submission is successful. Otherwise returns an appropriate error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563522">KsPinRegisterFrameReturnCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563530">KsPinSubmitFrameMdl</a>