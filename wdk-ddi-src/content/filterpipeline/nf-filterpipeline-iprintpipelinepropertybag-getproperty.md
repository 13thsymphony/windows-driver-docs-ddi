---
UID: NF.filterpipeline.IPrintPipelinePropertyBag.GetProperty
title: IPrintPipelinePropertyBag::GetProperty method
author: windows-driver-content
description: The GetProperty method gets a property from a property bag.
old-location: print\iprintpipelinepropertybag_getproperty.htm
old-project: print
ms.assetid: 10a5ada8-98ab-4e1c-a4b5-2f6d60674952
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPrintPipelinePropertyBag, IPrintPipelinePropertyBag::GetProperty, GetProperty
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
req.alt-api: IPrintPipelinePropertyBag.GetProperty
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

# IPrintPipelinePropertyBag::GetProperty method



## -description
The <code>GetProperty</code> method gets a property from a property bag.



## -syntax

````
HRESULT GetProperty(
  [in]  const wchar_t *pszName,
  [out]       VARIANT *pVar
);
````


## -parameters

### -param pszName [in]

The name of the property that you want to get from the property bag.


### -param pVar [out]

The <b>VARIANT</b> value to get from the property bag.


## -returns
<code>GetProperty</code> returns an <b>HRESULT</b> value.


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