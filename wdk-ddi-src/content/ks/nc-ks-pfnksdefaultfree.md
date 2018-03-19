---
UID: NC:ks.PFNKSDEFAULTFREE
title: PFNKSDEFAULTFREE
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniAllocatorFreeFrame routine frees the specified frame.
old-location: stream\avstrminiallocatorfreeframe.htm
old-project: stream
ms.assetid: ac8dd796-bc14-4b63-a0cb-5200cc1f0ce2
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: AVStrMiniAllocatorFreeFrame, AVStrMiniAllocatorFreeFrame routine [Streaming Media Devices], PFNKSDEFAULTFREE, avstclbk_c8c89d05-d36c-4a86-b92f-5465c1bc3eb2.xml, ks/AVStrMiniAllocatorFreeFrame, stream.avstrminiallocatorfreeframe
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
-	AVStrMiniAllocatorFreeFrame
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---


# PFNKSDEFAULTFREE callback function
An AVStream minidriver's <i>AVStrMiniAllocatorFreeFrame</i> routine frees the specified frame.

## Syntax

```
PFNKSDEFAULTFREE Pfnksdefaultfree;

void Pfnksdefaultfree(
  PVOID Context,
  PVOID Buffer
)
{...}
```

## Parameters

`Context`

Pointer to the allocator's context structure created in <a href="..\ks\nc-ks-pfnkspininitializeallocator.md">AVStrMiniInitializeAllocator</a>.

`Buffer`

Pointer to the frame to be freed.


## Return Value

None

## Remarks

The minidriver specifies this routine's address in the <b>Free</b> member of its <a href="..\ks\ns-ks-_ksallocator_dispatch.md">KSALLOCATOR_DISPATCH</a> structure. The minidriver passes this structure to the class driver in <a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a>.

AVStream calls <i>AVStrMiniFree</i> to free a frame, passing as parameters the context structure set in the initialization dispatch and a pointer to the frame to free.

For more information, see <a href="https://msdn.microsoft.com/07812703-a66f-450a-b28e-4cf765267c4a">KS Allocators</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="..\ks\nc-ks-pfnkspininitializeallocator.md">AVStrMiniInitializeAllocator</a>



<a href="..\ks\ns-ks-_ksallocator_dispatch.md">KSALLOCATOR_DISPATCH</a>