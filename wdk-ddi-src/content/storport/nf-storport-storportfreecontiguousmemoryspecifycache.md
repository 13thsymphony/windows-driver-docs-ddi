---
UID: NF.storport.StorPortFreeContiguousMemorySpecifyCache
title: StorPortFreeContiguousMemorySpecifyCache
author: windows-driver-content
description: The StorPortFreeContiguousMemorySpecifyCache routine deallocates a range of noncached memory in the nonpaged portion of the system address space.
old-location: storage\storportfreecontiguousmemoryspecifycache.htm
old-project: storage
ms.assetid: 29735ea8-6125-4958-8d78-12d1f13b16ea
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: StorPortFreeContiguousMemorySpecifyCache
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortFreeContiguousMemorySpecifyCache
req.alt-loc: storport.h
req.ddi-compliance: StorPortIrql
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# StorPortFreeContiguousMemorySpecifyCache function



## -description
<p>The <b>StorPortFreeContiguousMemorySpecifyCache</b> routine deallocates a range of noncached memory in the nonpaged portion of the system address space.</p>


## -syntax

````
ULONG StorPortFreeContiguousMemorySpecifyCache(
  _In_ PVOID               HwDeviceExtension,
  _In_ PVOID               BaseAddress,
  _In_ SIZE_T              NumberOfBytes,
  _In_ MEMORY_CACHING_TYPE CacheType
);
````


## -parameters
<dl>

### -param <i>HwDeviceExtension</i> [in]

<dd>
<p>A pointer to the hardware device extension for the host bus adapter (HBA).</p>
</dd>

### -param <i>BaseAddress</i> [in]

<dd>
<p>The base virtual address to free.</p>
</dd>

### -param <i>NumberOfBytes</i> [in]

<dd>
<p>The number of bytes that are allocated to the request. This must be the same number that was supplied as a parameter when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567027">StorPortAllocateContiguousMemorySpecifyCacheNode</a> routine was previously called.</p>
</dd>

### -param <i>CacheType</i> [in]

<dd>
<p>The cache type that is used in the call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567027">StorPortAllocateContiguousMemorySpecifyCacheNode</a> routine.</p>
</dd>
</dl>

## -returns
<p>The <b>StorPortFreeContiguousMemorySpecifyCache</b> routine returns one of the following status codes:</p><dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl><p>This function is not implemented on the active operating system.</p><dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl><p>The operation was successful.</p>

<p> </p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 7 and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;=DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh454266">StorPortIrql</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567027">StorPortAllocateContiguousMemorySpecifyCacheNode</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortFreeContiguousMemorySpecifyCache routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
