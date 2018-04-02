---
UID: NC:ks.PFNALLOCATOR_ALLOCATEFRAME
title: PFNALLOCATOR_ALLOCATEFRAME
author: windows-driver-content
description: The KStrAllocateFrame routine describes a vendor-supplied frame allocation function.
old-location: stream\kstrallocateframe.htm
old-project: stream
ms.assetid: 1b6eec23-82b4-4e8f-89d0-e76d6449906e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KStrAllocateFrame, KStrAllocateFrame routine [Streaming Media Devices], PFNALLOCATOR_ALLOCATEFRAME, ks/KStrAllocateFrame, ksfunc_a90af96e-53df-43f5-b847-ba1876b788fd.xml, stream.kstrallocateframe
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
-	KStrAllocateFrame
product:
- Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---


# PFNALLOCATOR_ALLOCATEFRAME callback function
The <i>KStrAllocateFrame</i> routine describes a vendor-supplied frame allocation function.

## Syntax

```
PFNALLOCATOR_ALLOCATEFRAME PfnallocatorAllocateframe;

NTSTATUS PfnallocatorAllocateframe(
  PFILE_OBJECT FileObject,
  PVOID *Frame
)
{...}
```

## Parameters

`FileObject`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a> structure for which to allocate frames.

`*Frame`

A pointer to a caller-allocated buffer in which the new frame is returned.


## Return Value

Returns STATUS_SUCCESS if the request is handled.  Otherwise returns an appropriate error code.

## Remarks

This type is used in the <b>AllocateFrame</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566862">KSSTREAMALLOCATOR_FUNCTIONTABLE</a> structure.

You can pass an instance of this structure as part of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565633">KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE</a> property request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565633">KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566862">KSSTREAMALLOCATOR_FUNCTIONTABLE</a>