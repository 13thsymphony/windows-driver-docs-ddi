---
UID: NC.ks.PFNKSDELETEALLOCATOR
title: PFNKSDELETEALLOCATOR
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniDeleteAllocator routine deletes the allocator that is associated with a pin.
old-location: stream\avstrminideleteallocator.htm
old-project: stream
ms.assetid: 867da1f8-061b-4fc1-8e20-3ebc43300f15
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: NpdBrokerUninitialize
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
req.alt-api: AVStrMiniDeleteAllocator
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
req.iface: 
---

# PFNKSDELETEALLOCATOR callback



## -description
<p>An AVStream minidriver's <i>AVStrMiniDeleteAllocator</i> routine deletes the allocator that is associated with a pin.</p>


## -prototype

````
PFNKSDELETEALLOCATOR AVStrMiniDeleteAllocator;

VOID AVStrMiniDeleteAllocator(
  _In_ PVOID Context
)
{ ... }
````


## -parameters
<dl>

### -param Context [in]

<dd>
<p>Pointer to the allocator's context structure created by <a href="stream.avstrminiinitializeallocator">AVStrMiniInitializeAllocator</a>.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The minidriver specifies this routine's address in the <b>DeleteAllocator</b> member of its <a href="..\ks\ns-ks--ksallocator-dispatch.md">KSALLOCATOR_DISPATCH</a> structure. The minidriver passes this structure to the class driver in <a href="..\ks\ns-ks--kspin-dispatch.md">KSPIN_DISPATCH</a>.</p>

<p>Once this function is called, AVStream will no longer use the allocator to allocate and free memory. This handler should release all system resources reserved by the allocator.</p>

<p>For more information, see <a href="https://msdn.microsoft.com/07812703-a66f-450a-b28e-4cf765267c4a">KS Allocators</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="stream.avstrminiinitializeallocator">AVStrMiniInitializeAllocator</a>
</dt>
<dt>
<a href="..\ks\ns-ks--ksallocator-dispatch.md">KSALLOCATOR_DISPATCH</a>
</dt>
<dt>
<a href="..\ks\ns-ks--kspin-dispatch.md">KSPIN_DISPATCH</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVStrMiniDeleteAllocator routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
