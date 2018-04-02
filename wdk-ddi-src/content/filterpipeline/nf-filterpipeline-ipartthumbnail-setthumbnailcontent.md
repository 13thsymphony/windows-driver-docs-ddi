---
UID: NF:filterpipeline.IPartThumbnail.SetThumbnailContent
title: IPartThumbnail::SetThumbnailContent method
author: windows-driver-content
description: The SetThumbnailContent method sets the thumbnail content for the part.
old-location: print\ipartthumbnail_setthumbnailcontent.htm
old-project: print
ms.assetid: 7392aa0b-479a-473f-b8b5-34e14494e050
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPartThumbnail, IPartThumbnail interface [Print Devices], SetThumbnailContent method, IPartThumbnail::SetThumbnailContent, SetThumbnailContent method [Print Devices], SetThumbnailContent method [Print Devices], IPartThumbnail interface, SetThumbnailContent,IPartThumbnail.SetThumbnailContent, filterpipeline/IPartThumbnail::SetThumbnailContent, filterpipeline_da595290-0b57-4b7d-a494-1f93b8f05470.xml, print.ipartthumbnail_setthumbnailcontent
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
-	IPartThumbnail.SetThumbnailContent
product:
- Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# IPartThumbnail::SetThumbnailContent method
The <b>SetThumbnailContent</b> method sets the thumbnail content for the part.

## Syntax

```
HRESULT SetThumbnailContent(
  const wchar_t *pContentType
);
```

## Parameters

`pContentType`




## Return Value

<b>SetThumbnailContent</b> returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | filterpipeline.h |