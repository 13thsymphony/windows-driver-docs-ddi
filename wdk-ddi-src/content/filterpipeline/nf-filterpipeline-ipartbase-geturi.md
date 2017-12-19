---
UID: NF.filterpipeline.IPartBase.GetUri
title: IPartBase::GetUri method
author: windows-driver-content
description: The GetUri method gets the URI of the part.
old-location: print\ipartbase_geturi.htm
old-project: print
ms.assetid: 5f4e3723-a30d-462d-9e7b-da05aa2e0b3c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPartBase, IPartBase::GetUri, GetUri
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPartBase.GetUri
req.alt-loc: filterpipeline.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Filterpipeline.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# IPartBase::GetUri method



## -description
The <b>GetUri</b> method gets the URI of the part.



## -syntax

````
HRESULT GetUri(
  [out] BSTR *uri
);
````


## -parameters

### -param uri [out]

The URI of the part.


## -returns
<b>GetUri</b> returns an <b>HRESULT</b> value.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Filterpipeline.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IDL

</th>
<td width="70%">
<dl>
<dt>Filterpipeline.idl</dt>
</dl>
</td>
</tr>
</table>