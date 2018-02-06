---
UID: NF:filterpipeline.IFixedDocument.GetUri
title: IFixedDocument::GetUri method
author: windows-driver-content
description: The GetUri method gets the URI of the fixed document.
old-location: print\ifixeddocument_geturi.htm
old-project: print
ms.assetid: ed19deff-ecb3-4c6c-bbf5-a82a27b5934e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IFixedDocument interface [Print Devices], GetUri method, print.ifixeddocument_geturi, GetUri, IFixedDocument, GetUri method [Print Devices], filterpipeline_278b5027-10e2-4564-a404-143f84e0123c.xml, filterpipeline/IFixedDocument::GetUri, IFixedDocument::GetUri, GetUri method [Print Devices], IFixedDocument interface
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
-	IFixedDocument.GetUri
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# GetUri method
The <b>GetUri</b> method gets the URI of the fixed document.

## Syntax

````
HRESULT GetUri(
  [out] BSTR *uri
);
````

## Parameters

`uri`

The URI of the fixed document.


## Return Value

<b>GetUri</b> returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | filterpipeline.h |
| **Library** | filterpipeline.h |