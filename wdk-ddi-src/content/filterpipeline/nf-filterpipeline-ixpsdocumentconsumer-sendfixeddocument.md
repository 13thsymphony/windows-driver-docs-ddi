---
UID: NF:filterpipeline.IXpsDocumentConsumer.SendFixedDocument
title: IXpsDocumentConsumer::SendFixedDocument method
author: windows-driver-content
description: The SendFixedDocument method sends a fixed document object to the pipeline.
old-location: print\ixpsdocumentconsumer_sendfixeddocument.htm
old-project: print
ms.assetid: 917dd9c3-5552-43d0-b396-9ba236f53132
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: SendFixedDocument method [Print Devices], IXpsDocumentConsumer interface, IXpsDocumentConsumer, print.ixpsdocumentconsumer_sendfixeddocument, IXpsDocumentConsumer::SendFixedDocument, SendFixedDocument method [Print Devices], filterpipeline_a6ecc63d-889e-4ae1-8031-16accffa9c2a.xml, SendFixedDocument, IXpsDocumentConsumer interface [Print Devices], SendFixedDocument method, filterpipeline/IXpsDocumentConsumer::SendFixedDocument
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Filterpipeline.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: filterpipeline.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	filterpipeline.h
apiname:
-	IXpsDocumentConsumer.SendFixedDocument
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# SendFixedDocument method
The <code>SendFixedDocument</code> method sends a fixed document object to the pipeline.

## Syntax

````
HRESULT SendFixedDocument(
  [in] IFixedDocument *pIFixedDocument
);
````

## Parameters

`pIFixedDocument`

A pointer to an XPS fixed document object.


## Return Value

<code>SendFixedDocument</code> returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | filterpipeline.h |
| **Library** | filterpipeline.h |