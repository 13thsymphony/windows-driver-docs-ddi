---
UID: NF:filterpipeline.IFixedPage.SetPagePart
title: IFixedPage::SetPagePart method
author: windows-driver-content
description: The SetPagePart method associates a new part with the page.
old-location: print\ifixedpage_setpagepart.htm
old-project: print
ms.assetid: 12970111-3d25-4004-9c6d-8582ef7afef3
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IFixedPage, IFixedPage::SetPagePart, SetPagePart
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
req.alt-api: IFixedPage.SetPagePart
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
req.typenames: EXpsFontRestriction
---

# IFixedPage::SetPagePart method



## -description
The <b>SetPagePart</b> method associates a new part with the page.



## -syntax

````
HRESULT SetPagePart(
  [in] IUnknown *pUnk
);
````


## -parameters

### -param pUnk [in]

A pointer to the new part.


## -returns
<b>SetPagePart</b> returns an <b>HRESULT</b> value.


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