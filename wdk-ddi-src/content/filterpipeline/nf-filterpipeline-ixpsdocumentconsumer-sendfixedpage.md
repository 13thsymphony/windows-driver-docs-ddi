---
UID : NF:filterpipeline.IXpsDocumentConsumer.SendFixedPage
title : IXpsDocumentConsumer::SendFixedPage method
author : windows-driver-content
description : The SendFixedPage method sends a fixed page of an XPS document to the pipeline.
old-location : print\ixpsdocumentconsumer_sendfixedpage.htm
old-project : print
ms.assetid : ef11161d-5e73-44a8-b802-e3706b78950e
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : IXpsDocumentConsumer, IXpsDocumentConsumer::SendFixedPage, SendFixedPage
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : filterpipeline.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IXpsDocumentConsumer.SendFixedPage
req.alt-loc : filterpipeline.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : Filterpipeline.idl
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : EXpsFontRestriction
---


# SendFixedPage method
The <code>SendFixedPage</code> method sends a fixed page of an XPS document to the pipeline.

## Syntax

````
HRESULT SendFixedPage(
  [in] IFixedPage *pIFixedPage
);
````

## Parameters

`pIFixedPage`

A pointer to an XPS fixed page object.


## Return Value

<code>SendFixedPage</code> returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | filterpipeline.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |