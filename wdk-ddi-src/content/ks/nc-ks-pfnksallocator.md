---
UID: NC.ks.PFNKSALLOCATOR
title: PFNKSALLOCATOR
author: windows-driver-content
description: Minidrivers can optionally supply a callback function of type PFNKSALLOCATOR as a parameter in calls to KsEnableEventWithAllocator, KsPropertyHandlerWithAllocator, and KsMethodHandlerWithAllocator.
old-location: stream\kstrallocator.htm
old-project: stream
ms.assetid: 4af5ac92-824c-42bf-8fb7-5418ae5d793c
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: NpdBrokerUninitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KStrAllocator
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

# PFNKSALLOCATOR callback



## -description
<p>Minidrivers can optionally supply a callback function of type <b>PFNKSALLOCATOR</b> as a parameter in calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff561733">KsEnableEventWithAllocator</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff564264">KsPropertyHandlerWithAllocator</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff563401">KsMethodHandlerWithAllocator</a>.</p>


## -prototype

````
PFNKSALLOCATOR KStrAllocator;

NTSTATUS KStrAllocator(
  _In_ PIRP  Irp,
  _In_ ULONG BufferSize,
  _In_ BOOL  InputOperation
)
{ ... }
````


## -parameters
<dl>

### -param <i>Irp</i> [in]

<dd>
<p>Specifies the IRP for which the buffer allocation request is being made.</p>
</dd>

### -param <i>BufferSize</i> [in]

<dd>
<p>Specifies the size of buffer needed. This size covers all parameters in the request.</p>
</dd>

### -param <i>InputOperation</i> [in]

<dd>
<p>Set to <b>TRUE</b> if this is an input operation, meaning that on successful return, the Irp-&gt;IoStatus.Information field will contain the number of bytes to copy back to the original input buffer.</p>
</dd>
</dl>

## -returns
<p>Returns STATUS_SUCCESS if the request is handled.  Otherwise returns an appropriate error code.</p>

## -remarks
<p>Typically, pool memory is used for buffer allocations. This enables filters that pass event, property, and method queries directly to hardware to avoid extra data copies by allowing them to provide the buffer into which such data is placed by the standard handling functions. So, a filter may have memory blocks that have already been mapped to an adapter from which buffer allocations can occur.</p>

<p>Since this memory presumably is not typical pool-allocated memory, the filter must perform buffer cleanup on completion of the Irp. This means that for input operations from usermode that are not synchronous, the allocator must allocate an MDL for the destination buffer, probe and lock it, and retrieve a system address. This must be done in order to enable copying of the return data to the original buffer.</p>

<p>Typically, pool memory is used for buffer allocations. This enables filters that pass event, property, and method queries directly to hardware to avoid extra data copies by allowing them to provide the buffer into which such data is placed by the standard handling functions. So, a filter may have memory blocks that have already been mapped to an adapter from which buffer allocations can occur.</p>

<p>Since this memory presumably is not typical pool-allocated memory, the filter must perform buffer cleanup on completion of the Irp. This means that for input operations from usermode that are not synchronous, the allocator must allocate an MDL for the destination buffer, probe and lock it, and retrieve a system address. This must be done in order to enable copying of the return data to the original buffer.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>