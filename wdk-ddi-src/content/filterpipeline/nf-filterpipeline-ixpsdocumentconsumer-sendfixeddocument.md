---
UID: NF:filterpipeline.IXpsDocumentConsumer.SendFixedDocument
title: IXpsDocumentConsumer::SendFixedDocument method
author: windows-driver-content
description: The SendFixedDocument method sends a fixed document object to the pipeline.
old-location: print\ixpsdocumentconsumer_sendfixeddocument.htm
old-project: print
ms.assetid: 917dd9c3-5552-43d0-b396-9ba236f53132
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IXpsDocumentConsumer, IXpsDocumentConsumer::SendFixedDocument, SendFixedDocument
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
req.alt-api: IXpsDocumentConsumer.SendFixedDocument
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

# IXpsDocumentConsumer::SendFixedDocument method



## -description
The <code>SendFixedDocument</code> method sends a fixed document object to the pipeline.



## -syntax

````
HRESULT SendFixedDocument(
  [in] IFixedDocument *pIFixedDocument
);
````


## -parameters

### -param pIFixedDocument [in]

A pointer to an XPS fixed document object.


## -returns
<code>SendFixedDocument</code> returns an <b>HRESULT</b> value.


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