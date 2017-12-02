---
UID: NF.filterpipeline.IFixedPage.GetPagePart
title: IFixedPage::GetPagePart
author: windows-driver-content
description: The GetPagePart method gets the images, thumbnails, fonts, and so on in a page by using the URI.
old-location: print\ifixedpage_getpagepart.htm
old-project: print
ms.assetid: 6ec8d282-eedb-419e-84cb-8f4776ea7650
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: IFixedPage, GetPagePart, IFixedPage::GetPagePart
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
req.alt-api: IFixedPage.GetPagePart
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
req.iface: IFixedPage
---

# IFixedPage::GetPagePart method



## -description
<p>The <b>GetPagePart</b> method gets the images, thumbnails, fonts, and so on in a page by using the URI.</p>


## -syntax

````
HRESULT GetPagePart(
  [in]  const wchar_t  *uri,
  [out]       IUnknown **ppUnk
);
````


## -parameters
<dl>

### -param uri [in]

<dd>
<p>The URI for a part. For example, the filter might parse the page markup and find a referenced font. The filter can use the font URI in a call to <b>GetPagePart</b>. The filter could then retrieve the font object that is associated with the page.</p>
</dd>

### -param ppUnk [out]

<dd>
<p>The object that is to be queried.</p>
</dd>
</dl>

## -returns
<p><b>GetPagePart</b> returns an <b>HRESULT</b>.</p>

## -remarks
<p>A filter must use QueryInterface on the return value to see what part types reside in the page.</p>

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