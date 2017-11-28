---
UID: NF.ks.KsCreateAllocator
title: KsCreateAllocator
author: windows-driver-content
description: The KsCreateAllocator function creates a handle to an allocator for the given sink connection handle. This function does not complete the IRP or set the status in the IRP.
old-location: stream\kscreateallocator.htm
old-project: stream
ms.assetid: c67e036c-9f4c-447e-94bb-73cf215c865a
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: KsCreateAllocator
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsCreateAllocator
req.alt-loc: ks.lib,ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL (See Remarks section)
req.iface: 
---

# KsCreateAllocator function



## -description
<p>The <b>KsCreateAllocator</b> function creates a handle to an allocator for the given sink connection handle. This function does not complete the IRP or set the status in the IRP.</p>


## -syntax

````
NTSTATUS KsCreateAllocator(
  _In_  HANDLE               ConnectionHandle,
  _In_  PKSALLOCATOR_FRAMING AllocatorFraming,
  _Out_ PHANDLE              AllocatorHandle
);
````


## -parameters
<dl>

### -param <i>ConnectionHandle</i> [in]

<dd>
<p>Specifies the handle to the sink connection on which to create the allocator.</p>
</dd>

### -param <i>AllocatorFraming</i> [in]

<dd>
<p>Specified framing for the allocator.</p>
</dd>

### -param <i>AllocatorHandle</i> [out]

<dd>
<p>Specifies the pointer to a handle to store the allocator handle.</p>
</dd>
</dl>

## -returns
<p>The <b>KsCreateAllocator</b> function returns STATUS_SUCCESS if successful, or it returns an error if unsuccessful. </p>

## -remarks
<p>There are two versions of the <b>KsCreateAllocator</b> function: one for user-mode clients and one for kernel-mode clients. This function can only be called at PASSIVE_LEVEL for kernel-mode clients.</p>

<p>There are two versions of the <b>KsCreateAllocator</b> function: one for user-mode clients and one for kernel-mode clients. This function can only be called at PASSIVE_LEVEL for kernel-mode clients.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL (See Remarks section)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560979">KSALLOCATOR_FRAMING</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsCreateAllocator function%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
