---
UID: NF:filterpipeline.IPartImage.SetImageContent
title: IPartImage::SetImageContent method
author: windows-driver-content
description: The SetImageContent method sets an image property that is based on the content type.
old-location: print\ipartimage_setimagecontent.htm
old-project: print
ms.assetid: 5d7a59ac-93de-4a41-9313-df189e1f6e36
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPartImage, IPartImage interface [Print Devices], SetImageContent method, IPartImage::SetImageContent, SetImageContent method [Print Devices], SetImageContent method [Print Devices], IPartImage interface, SetImageContent,IPartImage.SetImageContent, filterpipeline/IPartImage::SetImageContent, filterpipeline_1bbf6da0-f016-486d-a06d-768614fe1d5a.xml, print.ipartimage_setimagecontent
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	filterpipeline.h
api_name:
-	IPartImage.SetImageContent
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# SetImageContent method
The <b>SetImageContent</b> method sets an image property that is based on the content type.

## Syntax

````
HRESULT SetImageContent(
  [in] const wchar_t *contentType
);
````

## Parameters

`pContentType`




## Return Value

<b>SetImageContent</b> returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | filterpipeline.h |
| **Library** | filterpipeline.h |