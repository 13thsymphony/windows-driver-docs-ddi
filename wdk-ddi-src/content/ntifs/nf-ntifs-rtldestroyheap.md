---
UID: NF.ntifs.RtlDestroyHeap
title: RtlDestroyHeap function
author: windows-driver-content
description: The RtlDestroyHeap routine destroys the specified heap object. RtlDestroyHeap decommits and releases all the pages of a private heap object, and it invalidates the handle to the heap.
old-location: ifsk\rtldestroyheap.htm
old-project: ifsk
ms.assetid: e62855a0-284b-434b-88a4-1f21f1b77cf2
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RtlDestroyHeap
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlDestroyHeap
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: < DISPATCH_LEVEL
---

# RtlDestroyHeap function



## -description
The <b>RtlDestroyHeap</b> routine destroys the specified heap object. <b>RtlDestroyHeap</b> decommits and releases all the pages of a private heap object, and it invalidates the handle to the heap. 


## -syntax

````
PVOID RtlDestroyHeap(
  _In_ PVOID HeapHandle
);
````


## -parameters

### -param HeapHandle [in]

Handle for the heap to be destroyed. This parameter is a heap handle returned by <b>RtlCreateHeap</b>. 

## -returns
If the call to <b>RtlDestroyHeap</b> succeeds, the return value is a <b>NULL</b> pointer. 

If the call to <b>RtlDestroyHeap</b> fails, the return value is a handle for the heap. 

## -remarks
Processes can call <b>RtlDestroyHeap</b> without first calling <b>RtlFreeHeap</b> to free memory that was allocated from the heap. 

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
This routine is available on Microsoft Windows XP and later. 
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt; DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.rtlallocateheap">RtlAllocateHeap</a>
</dt>
<dt>
<a href="ifsk.rtlcreateheap">RtlCreateHeap</a>
</dt>
<dt>
<a href="ifsk.rtlfreeheap">RtlFreeHeap</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlDestroyHeap routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
