---
UID: NF.filterpipeline.IPartThumbnail.SetThumbnailContent
title: IPartThumbnail::SetThumbnailContent method
author: windows-driver-content
description: The SetThumbnailContent method sets the thumbnail content for the part.
old-location: print\ipartthumbnail_setthumbnailcontent.htm
old-project: print
ms.assetid: 7392aa0b-479a-473f-b8b5-34e14494e050
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPartThumbnail, IPartThumbnail::SetThumbnailContent, SetThumbnailContent
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
---

# IPartThumbnail::SetThumbnailContent method



## -description
The <b>SetThumbnailContent</b> method sets the thumbnail content for the part.



## -syntax

````
HRESULT SetThumbnailContent(
  [in] const wchar_t *contentType
);
````


## -parameters

### -param contentType [in]

The type of content for the thumbnail.


## -returns
<b>SetThumbnailContent</b> returns an <b>HRESULT</b> value.


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