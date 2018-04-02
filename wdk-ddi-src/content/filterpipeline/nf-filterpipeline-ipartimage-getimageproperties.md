---
UID: NF:filterpipeline.IPartImage.GetImageProperties
title: IPartImage::GetImageProperties method
author: windows-driver-content
description: The GetImageProperties method gets an image property that is based on the content type.
old-location: print\ipartimage_getimageproperties.htm
old-project: print
ms.assetid: 7ce333a3-86a2-47e5-b755-fd84469c8785
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetImageProperties method [Print Devices], GetImageProperties method [Print Devices], IPartImage interface, GetImageProperties,IPartImage.GetImageProperties, IPartImage, IPartImage interface [Print Devices], GetImageProperties method, IPartImage::GetImageProperties, filterpipeline/IPartImage::GetImageProperties, filterpipeline_06d3e014-e30a-44d2-a6e0-769cb62c387d.xml, print.ipartimage_getimageproperties
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
-	IPartImage.GetImageProperties
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# IPartImage::GetImageProperties method
The <b>GetImageProperties</b> method gets an image property that is based on the content type.

## Syntax

```
HRESULT GetImageProperties(
  BSTR *pContentType
);
```

## Parameters

`pContentType`

The type of content for the image.


## Return Value

<b>GetImageProperties</b> returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | filterpipeline.h |