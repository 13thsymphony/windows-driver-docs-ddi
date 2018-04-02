---
UID: NC:ks.PFNKSDELETEALLOCATOR
title: PFNKSDELETEALLOCATOR
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniDeleteAllocator routine deletes the allocator that is associated with a pin.
old-location: stream\avstrminideleteallocator.htm
old-project: stream
ms.assetid: 867da1f8-061b-4fc1-8e20-3ebc43300f15
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: AVStrMiniDeleteAllocator, AVStrMiniDeleteAllocator routine [Streaming Media Devices], PFNKSDELETEALLOCATOR, avstclbk_32e3c0fd-c437-45e0-8e5e-72f2f628ee51.xml, ks/AVStrMiniDeleteAllocator, stream.avstrminideleteallocator
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
-	AVStrMiniDeleteAllocator
product:
- Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---


# PFNKSDELETEALLOCATOR callback function
An AVStream minidriver's <i>AVStrMiniDeleteAllocator</i> routine deletes the allocator that is associated with a pin.

## Syntax

```
PFNKSDELETEALLOCATOR Pfnksdeleteallocator;

void Pfnksdeleteallocator(
  PVOID Context
)
{...}
```

## Parameters

`Context`

Pointer to the allocator's context structure created by <a href="https://msdn.microsoft.com/library/windows/hardware/ff556321">AVStrMiniInitializeAllocator</a>.


## Return Value

None

## Remarks

The minidriver specifies this routine's address in the <b>DeleteAllocator</b> member of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff560976">KSALLOCATOR_DISPATCH</a> structure. The minidriver passes this structure to the class driver in <a href="https://msdn.microsoft.com/library/windows/hardware/ff563535">KSPIN_DISPATCH</a>.

Once this function is called, AVStream will no longer use the allocator to allocate and free memory. This handler should release all system resources reserved by the allocator.

For more information, see <a href="https://msdn.microsoft.com/07812703-a66f-450a-b28e-4cf765267c4a">KS Allocators</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556321">AVStrMiniInitializeAllocator</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560976">KSALLOCATOR_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563535">KSPIN_DISPATCH</a>