---
UID: NS:ks._KSALLOCATOR_DISPATCH
title: "_KSALLOCATOR_DISPATCH"
author: windows-driver-content
description: The KSALLOCATOR_DISPATCH structure contains the callbacks required for a pin to implement its own kernel-level allocator.
old-location: stream\ksallocator_dispatch.htm
old-project: stream
ms.assetid: 6e6e6dde-3b41-44a7-b51d-1b1f06db0853
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSALLOCATOR_DISPATCH, KSALLOCATOR_DISPATCH, KSALLOCATOR_DISPATCH structure [Streaming Media Devices], PKSALLOCATOR_DISPATCH, PKSALLOCATOR_DISPATCH structure pointer [Streaming Media Devices], _KSALLOCATOR_DISPATCH, avstruct_73d2c793-a55a-45f3-af31-fc18240ca1df.xml, ks/KSALLOCATOR_DISPATCH, ks/PKSALLOCATOR_DISPATCH, stream.ksallocator_dispatch"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSALLOCATOR_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: KSALLOCATOR_DISPATCH, *PKSALLOCATOR_DISPATCH
---

# _KSALLOCATOR_DISPATCH structure
The KSALLOCATOR_DISPATCH structure contains the callbacks required for a pin to implement its own kernel-level allocator.

## Syntax
```
typedef struct _KSALLOCATOR_DISPATCH {
  PFNKSPININITIALIZEALLOCATOR InitializeAllocator;
  PFNKSDELETEALLOCATOR        DeleteAllocator;
  PFNKSDEFAULTALLOCATE        Allocate;
  PFNKSDEFAULTFREE            Free;
} KSALLOCATOR_DISPATCH, *PKSALLOCATOR_DISPATCH;
```

## Members


`InitializeAllocator`

A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556321">AVStrMiniInitializeAllocator</a> callback routine.

`DeleteAllocator`

A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff554273">AVStrMiniDeleteAllocator</a> callback routine.

`Allocate`

A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff554265">AVStrMiniAllocate</a> callback routine.

`Free`

A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff554266">AVStrMiniAllocatorFreeFrame</a> callback routine.

## Remarks
By providing a pointer to a KSALLOCATOR_DISPATCH structure in the relevant <a href="https://msdn.microsoft.com/library/windows/hardware/ff563535">KSPIN_DISPATCH</a> structure, a minidriver declares that the corresponding pin is capable of performing kernel-level allocation. The allocator might or might not be used by the graph manager. Note that memory allocated at kernel level cannot be passed to a user-mode filter.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions. Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions. |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563535">KSPIN_DISPATCH</a>