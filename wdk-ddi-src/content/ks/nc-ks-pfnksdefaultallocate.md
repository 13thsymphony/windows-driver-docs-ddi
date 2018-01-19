---
UID : NC:ks.PFNKSDEFAULTALLOCATE
title : PFNKSDEFAULTALLOCATE
author : windows-driver-content
description : An AVStream minidriver's AVStrMiniAllocate routine allocates a frame using the allocator specified in the Context parameter.
old-location : stream\avstrminiallocate.htm
old-project : stream
ms.assetid : f718e788-306a-4dbc-96cb-a81299aafe1d
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : NpdBrokerUninitialize
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : ks.h
req.include-header : Ks.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : AVStrMiniAllocate
req.alt-loc : ks.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : KEYWORDSELECTOR
---


# PFNKSDEFAULTALLOCATE callback function
An AVStream minidriver's <i>AVStrMiniAllocate</i> routine allocates a frame using the allocator specified in the <i>Context</i> parameter.

## Syntax

```
PFNKSDEFAULTALLOCATE Pfnksdefaultallocate;

PVOID Pfnksdefaultallocate(
  PVOID Context
)
{...}
```

## Parameters

`Context`

Pointer to the allocator's context structure created in <i>AVStrMiniInitializeAllocator</i>.


## Return Value

<b>Allocate</b> returns a pointer to the newly allocated memory. Return <b>NULL</b> if the attempt to allocate memory failed.

## Remarks

The minidriver specifies this routine's address in the <b>Allocate</b> member of its <a href="..\ks\ns-ks-_ksallocator_dispatch.md">KSALLOCATOR_DISPATCH</a> structure. The minidriver passes this structure to the class driver in <a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a>.

AVStream calls this routine to allocate a frame. The handler should allocate a frame as described by the allocator framing context passed into the initialization dispatch.

For more information, see <a href="https://msdn.microsoft.com/07812703-a66f-450a-b28e-4cf765267c4a">KS Allocators</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ks\nc-ks-pfnkspininitializeallocator.md">AVStrMiniInitializeAllocator</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_ksallocator_dispatch.md">KSALLOCATOR_DISPATCH</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSDEFAULTALLOCATE routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>