---
UID: NF.filterpipeline.IPartImage.SetImageContent
title: IPartImage::SetImageContent method
author: windows-driver-content
description: The SetImageContent method sets an image property that is based on the content type.
old-location: print\ipartimage_setimagecontent.htm
old-project: print
ms.assetid: 5d7a59ac-93de-4a41-9313-df189e1f6e36
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPartImage, IPartImage::SetImageContent, SetImageContent
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
req.alt-api: IPartImage.SetImageContent
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

# IPartImage::SetImageContent method



## -description
The <b>SetImageContent</b> method sets an image property that is based on the content type.



## -syntax

````
HRESULT SetImageContent(
  [in] const wchar_t *contentType
);
````


## -parameters

### -param contentType [in]

The type of content of the image.


## -returns
<b>SetImageContent</b> returns an <b>HRESULT</b> value.


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