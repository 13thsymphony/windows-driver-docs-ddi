---
UID: NF.ks.KsLoadResource
title: KsLoadResource function
author: windows-driver-content
description: Copies (loads) a resource from the given image.
old-location: stream\ksloadresource.htm
old-project: stream
ms.assetid: a7b9dcca-ce89-4fde-9e58-3c4a675227bc
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsLoadResource
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
req.alt-api: KsLoadResource
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

# KsLoadResource function



## -description
Copies (loads) a resource from the given image. 



## -syntax

````
NTSTATUS KsLoadResource(
  _In_      PVOID     ImageBase,
  _In_      POOL_TYPE PoolType,
  _In_      ULONG_PTR ResourceName,
  _In_      ULONG     ResourceType,
  _Out_     PVOID     *Resource,
  _Out_opt_ PULONG    ResourceSize
);
````


## -parameters

### -param ImageBase [in]

Pointer to the image base


### -param PoolType [in]

Pool type to use when copying resource


### -param ResourceName [in]

Resource name.


### -param ResourceType [in]

Resource type


### -param Resource [out]

Pointer to resultant resource memory.


### -param ResourceSize [out, optional]

Pointer to ULONG value to receive the size of the resource.


## -returns
STATUS_SUCCESS if successful, STATUS_INSUFFICIENT_RESOURCES if memory cannot be allocated, otherwise an appropriate error code.


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