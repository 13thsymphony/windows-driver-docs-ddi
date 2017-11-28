---
UID: NF.filterpipeline.IPartThumbnail.SetThumbnailContent
title: IPartThumbnail::SetThumbnailContent
author: windows-driver-content
description: The SetThumbnailContent method sets the thumbnail content for the part.
old-location: print\ipartthumbnail_setthumbnailcontent.htm
old-project: print
ms.assetid: 7392aa0b-479a-473f-b8b5-34e14494e050
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: IPartThumbnail, SetThumbnailContent, IPartThumbnail::SetThumbnailContent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPartThumbnail.SetThumbnailContent
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
req.iface: IPartThumbnail
---

# IPartThumbnail::SetThumbnailContent method



## -description
<p>The <b>SetThumbnailContent</b> method sets the thumbnail content for the part.</p>


## -syntax

````
HRESULT SetThumbnailContent(
  [in] const wchar_t *contentType
);
````


## -parameters
<dl>

### -param <i>contentType</i> [in]

<dd>
<p>The type of content for the thumbnail.</p>
</dd>
</dl>

## -returns
<p><b>SetThumbnailContent</b> returns an <b>HRESULT</b> value.</p>

## -remarks


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
<dt>Filterpipeline.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IDL</p>
</th>
<td width="70%">
<dl>
<dt>Filterpipeline.idl</dt>
</dl>
</td>
</tr>
</table>