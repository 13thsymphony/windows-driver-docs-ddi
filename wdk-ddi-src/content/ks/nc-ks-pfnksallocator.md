---
UID: NC:ks.PFNKSALLOCATOR
title: PFNKSALLOCATOR
author: windows-driver-content
description: Minidrivers can optionally supply a callback function of type PFNKSALLOCATOR as a parameter in calls to KsEnableEventWithAllocator, KsPropertyHandlerWithAllocator, and KsMethodHandlerWithAllocator.
old-location: stream\kstrallocator.htm
old-project: stream
ms.assetid: 4af5ac92-824c-42bf-8fb7-5418ae5d793c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KStrAllocator, KStrAllocator routine [Streaming Media Devices], PFNKSALLOCATOR, ks/KStrAllocator, ksfunc_abd9491e-0ad2-4c28-bd96-90ecd6a6af3c.xml, stream.kstrallocator
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
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
-	UserDefined
api_location:
-	ks.h
api_name:
-	KStrAllocator
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---


# PFNKSALLOCATOR callback function
Minidrivers can optionally supply a callback function of type <b>PFNKSALLOCATOR</b> as a parameter in calls to <a href="..\ks\nf-ks-ksenableeventwithallocator.md">KsEnableEventWithAllocator</a>, <a href="..\ks\nf-ks-kspropertyhandlerwithallocator.md">KsPropertyHandlerWithAllocator</a>, and <a href="..\ks\nf-ks-ksmethodhandlerwithallocator.md">KsMethodHandlerWithAllocator</a>.

## Syntax

```
PFNKSALLOCATOR Pfnksallocator;

NTSTATUS Pfnksallocator(
  PIRP Irp,
  ULONG BufferSize,
  BOOLEAN InputOperation
)
{...}
```

## Parameters

`Irp`

Specifies the IRP for which the buffer allocation request is being made.

`BufferSize`

Specifies the size of buffer needed. This size covers all parameters in the request.

`InputOperation`

Set to <b>TRUE</b> if this is an input operation, meaning that on successful return, the Irp-&gt;IoStatus.Information field will contain the number of bytes to copy back to the original input buffer.


## Return Value

Returns STATUS_SUCCESS if the request is handled.  Otherwise returns an appropriate error code.

## Remarks

Typically, pool memory is used for buffer allocations. This enables filters that pass event, property, and method queries directly to hardware to avoid extra data copies by allowing them to provide the buffer into which such data is placed by the standard handling functions. So, a filter may have memory blocks that have already been mapped to an adapter from which buffer allocations can occur.

Since this memory presumably is not typical pool-allocated memory, the filter must perform buffer cleanup on completion of the Irp. This means that for input operations from usermode that are not synchronous, the allocator must allocate an MDL for the destination buffer, probe and lock it, and retrieve a system address. This must be done in order to enable copying of the return data to the original buffer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |