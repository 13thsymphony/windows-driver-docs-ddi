---
UID: NF.ks.KsAllocateExtraData
title: KsAllocateExtraData function
author: windows-driver-content
description: The KsAllocateExtraData function is used with streaming IRPs to allocate a buffer to contain additional header data. A pointer to the allocated buffer is returned, and the buffer must eventually be freed by the caller.
old-location: stream\ksallocateextradata.htm
old-project: stream
ms.assetid: dfeaca74-d34d-4128-bd76-3a1bf1b3f5d6
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsAllocateExtraData
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
req.alt-api: KsAllocateExtraData
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: < DISPATCH_LEVEL
---

# KsAllocateExtraData function



## -description
The <b>KsAllocateExtraData</b> function is used with streaming IRPs to allocate a buffer to contain additional header data. A pointer to the allocated buffer is returned, and the buffer must eventually be freed by the caller. 


## -syntax

````
NTSTATUS KsAllocateExtraData(
  _Inout_ PIRP  Irp ,
  _In_    ULONG ExtraSize ,
  _Out_   PVOID *ExtraBuffer 
);
````


## -parameters

### -param Irp  [in, out]

Specifies the IRP containing the stream headers. The IRP must have been previously passed to <b>KsProbeStreamIrp</b> to buffer the headers.

### -param ExtraSize  [in]

Specifies the size, in bytes, of additional memory to allocate between each stream header. This value <i>must</i> be alignable on an eight-byte boundary. A copy of the headers is placed in the returned buffer, with the extra data size inserted between each header. This must be freed by the caller.

### -param ExtraBuffer  [out]

Points to a caller-allocated pointer that, on successful completion, points to a system-allocated buffer containing the stream headers and the requested padding between them. This must be freed by the caller.

## -returns
The <b>KsAllocateExtraData</b> function returns STATUS_SUCCESS if successful, or it returns a resource or access error.

## -remarks
When <b>KsAllocateExtraData</b> completes successfully, a pointer to a block of memory is returned that contains both the stream data headers from the IRP, specified at <i>Irp</i>, and padding between each header of size specified in <i>ExtraSize</i>. An example of such a resultant buffer is shown below:

When the extra buffer is no longer needed, the memory should be freed using <b>ExFreePool</b>.

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
Header
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
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