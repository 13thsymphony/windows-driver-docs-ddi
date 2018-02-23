---
UID: NC:ks.PFNKSPININITIALIZEALLOCATOR
title: PFNKSPININITIALIZEALLOCATOR
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniInitializeAllocator routine initializes an allocator that will be associated with a pin.
old-location: stream\avstrminiinitializeallocator.htm
old-project: stream
ms.assetid: 9c6d3856-702c-416b-a5d2-b3578a55bbcd
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: stream.avstrminiinitializeallocator, AVStrMiniInitializeAllocator, AVStrMiniInitializeAllocator routine [Streaming Media Devices], AVStrMiniInitializeAllocator, PFNKSPININITIALIZEALLOCATOR, PFNKSPININITIALIZEALLOCATOR, ks/AVStrMiniInitializeAllocator, avstclbk_979c0a29-7e4b-463c-8ff3-62124b0d49d1.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ks.h
apiname:
-	AVStrMiniInitializeAllocator
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---


# PFNKSPININITIALIZEALLOCATOR callback function
An AVStream minidriver's <i>AVStrMiniInitializeAllocator</i> routine initializes an allocator that will be associated with a pin.

## Syntax

```
PFNKSPININITIALIZEALLOCATOR Pfnkspininitializeallocator;

NTSTATUS Pfnkspininitializeallocator(
  PKSPIN Pin,
  PKSALLOCATOR_FRAMING AllocatorFraming,
  PVOID *Context
)
{...}
```

## Parameters

`Pin`

Pointer to a <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure describing the pin with which the allocator is to be associated.

`AllocatorFraming`

Pointer to a <a href="..\ks\ns-ks-ksallocator_framing.md">KSALLOCATOR_FRAMING</a> structure describing the framing requirements that the allocator should use.

`*Context`

Pointer to a context for the allocator that will be passed as a parameter to the other routines for this structure. For example, the driver could store pin or allocator framing structures for later reference by the other callback routines. Note that other routines for <a href="..\ks\ns-ks-_ksallocator_dispatch.md">KSALLOCATOR_DISPATCH</a> must have at least an indirect way of referencing <i>Pin</i>. (For instance, <a href="..\ks\nc-ks-pfnksdefaultallocate.md">AVStrMiniAllocate</a> will need to be able to access the <i>AllocatorFraming</i> information for <i>Pin</i>, and <i>Context</i> is the only parameter that AVStream will pass it.)


## Return Value

<i>AVStrMiniInitializeAllocator</i> should return STATUS_SUCCESS or the error code that it received attempting to create the allocator.

## Remarks

The minidriver specifies this routine's address in the <b>InitializeAllocator</b> member of its <a href="..\ks\ns-ks-_ksallocator_dispatch.md">KSALLOCATOR_DISPATCH</a> structure. The minidriver passes this structure to the class driver in <a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a>.

Note that kernel-mode allocators cannot allocate frames that could eventually reach user mode.

AVStream calls <i>AVStrMiniInitializeAllocator</i> to initialize the given allocator. The handler for this routine should prepare to handle memory allocation and free requests.

For more information, see <a href="https://msdn.microsoft.com/07812703-a66f-450a-b28e-4cf765267c4a">KS Allocators</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="..\ks\nc-ks-pfnksdeleteallocator.md">AVStrMiniDeleteAllocator</a>



<a href="..\ks\ns-ks-_kspin.md">KSPIN</a>







<a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a>



<a href="..\ks\ns-ks-ksallocator_framing.md">KSALLOCATOR_FRAMING</a>





<a href="..\ks\ns-ks-ksallocator_framing.md">KSALLOCATOR_FRAMING</a>



<a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSPININITIALIZEALLOCATOR routine%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>