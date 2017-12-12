---
UID: NS.KS._KSALLOCATOR_DISPATCH
title: _KSALLOCATOR_DISPATCH
author: windows-driver-content
description: The KSALLOCATOR_DISPATCH structure contains the callbacks required for a pin to implement its own kernel-level allocator.
old-location: stream\ksallocator_dispatch.htm
old-project: stream
ms.assetid: 6e6e6dde-3b41-44a7-b51d-1b1f06db0853
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _KSALLOCATOR_DISPATCH, *PKSALLOCATOR_DISPATCH, KSALLOCATOR_DISPATCH
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
req.alt-api: KSALLOCATOR_DISPATCH
req.alt-loc: ks.h
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
---

# _KSALLOCATOR_DISPATCH structure



## -description
The KSALLOCATOR_DISPATCH structure contains the callbacks required for a pin to implement its own kernel-level allocator.



## -syntax

````
typedef struct _KSALLOCATOR_DISPATCH {
  PFNKSPININITIALIZEALLOCATOR InitializeAllocator;
  PFNKSDELETEALLOCATOR        DeleteAllocator;
  PFNKSDEFAULTALLOCATE        Allocate;
  PFNKSDEFAULTFREE            Free;
} KSALLOCATOR_DISPATCH, *PKSALLOCATOR_DISPATCH;
````


## -struct-fields

### -field InitializeAllocator

A pointer to a minidriver-supplied <a href="stream.avstrminiinitializeallocator">AVStrMiniInitializeAllocator</a> callback routine.


### -field DeleteAllocator

A pointer to a minidriver-supplied <a href="stream.avstrminideleteallocator">AVStrMiniDeleteAllocator</a> callback routine.


### -field Allocate

A pointer to a minidriver-supplied <a href="stream.avstrminiallocate">AVStrMiniAllocate</a> callback routine.


### -field Free

A pointer to a minidriver-supplied <a href="stream.avstrminiallocatorfreeframe">AVStrMiniAllocatorFreeFrame</a> callback routine.


## -remarks
By providing a pointer to a KSALLOCATOR_DISPATCH structure in the relevant <a href="stream.kspin_dispatch">KSPIN_DISPATCH</a> structure, a minidriver declares that the corresponding pin is capable of performing kernel-level allocation. The allocator might or might not be used by the graph manager. Note that memory allocated at kernel level cannot be passed to a user-mode filter.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.kspin_dispatch">KSPIN_DISPATCH</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSALLOCATOR_DISPATCH structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

