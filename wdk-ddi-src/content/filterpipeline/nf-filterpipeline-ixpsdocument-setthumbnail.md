---
UID: NF:filterpipeline.IXpsDocument.SetThumbnail
title: IXpsDocument::SetThumbnail method
author: windows-driver-content
description: The SetThumbnail method removes the current thumbnail object from the document and inserts a new one.
old-location: print\ixpsdocument_setthumbnail.htm
old-project: print
ms.assetid: 47211c8f-e112-47fd-bd9e-57ff7ec586a5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IXpsDocument, IXpsDocument interface [Print Devices], SetThumbnail method, IXpsDocument::SetThumbnail, SetThumbnail method [Print Devices], SetThumbnail method [Print Devices], IXpsDocument interface, SetThumbnail,IXpsDocument.SetThumbnail, filterpipeline/IXpsDocument::SetThumbnail, filterpipeline_ee7609e5-4e6f-4619-aa3f-dfa217d5eabc.xml, print.ixpsdocument_setthumbnail
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	filterpipeline.h
api_name:
-	IXpsDocument.SetThumbnail
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# SetThumbnail method
The <code>SetThumbnail</code> method removes the current thumbnail object from the document and inserts a new one.

## Syntax

````
HRESULT SetThumbnail(
  [in] IPartThumbnail *pThumbnail
);
````

## Parameters

`pThumbnail`

A pointer to a new thumbnail.


## Return Value

<code>SetThumbnail</code> returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | filterpipeline.h |