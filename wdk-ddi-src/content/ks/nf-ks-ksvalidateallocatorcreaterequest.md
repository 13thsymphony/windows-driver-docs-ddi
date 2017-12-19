---
UID: NF.ks.KsValidateAllocatorCreateRequest
title: KsValidateAllocatorCreateRequest function
author: windows-driver-content
description: The KsValidateAllocatorCreateRequest function validates an IRP_MJ_CREATE request as an allocator request and returns the create structure associated with the request on success.
old-location: stream\ksvalidateallocatorcreaterequest.htm
old-project: stream
ms.assetid: 9275257b-50d8-4272-b340-4344644b3e15
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KsValidateAllocatorCreateRequest
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
req.alt-api: KsValidateAllocatorCreateRequest
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
req.irql: 
---

# KsValidateAllocatorCreateRequest function



## -description
The <b>KsValidateAllocatorCreateRequest</b> function validates an IRP_MJ_CREATE request as an allocator request and returns the create structure associated with the request on success.



## -syntax

````
NTSTATUS KsValidateAllocatorCreateRequest(
  _In_  PIRP                 Irp,
  _Out_ PKSALLOCATOR_FRAMING *AllocatorFraming
);
````


## -parameters

### -param Irp [in]

Specifies the IRP with the IRP_MJ_CREATE request being validated.


### -param AllocatorFraming [out]

Caller-defined pointer that on successful completion contains an address to the framing structure supplied with the request.


## -returns
The <b>KsValidateAllocatorCreateRequest</b> function returns STATUS_SUCCESS if successful, or an error if the allocator request is not valid.


## -remarks


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
</table>