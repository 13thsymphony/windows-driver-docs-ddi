---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlAllocateResource
title: FsRtlAllocateResource function
author: windows-driver-content
description: Obsolete.
old-location: ifsk\fsrtlallocateresource.htm
old-project: ifsk
ms.assetid: a02f87ea-e7e5-48ff-94a2-a76b4f0cd04a
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlAllocateResource
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlAllocateResource
req.alt-loc: ntifs.h
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
req.typenames: TOKEN_TYPE
---

# FsRtlAllocateResource function



## -description
The <b>FsRtlAllocateResource</b> routine is obsolete, but is exported to support existing driver binaries. Use <a href="..\wdm\nf-wdm-exallocatefromnpagedlookasidelist.md">ExAllocateFromNPagedLookasideList</a> and <a href="..\wdm\nf-wdm-exinitializeresourcelite.md">ExInitializeResourceLite</a> instead.



## -syntax

````
  FsRtlAllocateResource(
    
);
````


## -parameters

### -param  

Reserved.


## -remarks


## -requirements
<table>
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
</table>