---
UID : NF:filterpipeline.IPartFont.GetFontProperties
title : IPartFont::GetFontProperties method
author : windows-driver-content
description : The GetFontProperties method gets the font properties.
old-location : print\ipartfont_getfontproperties.htm
old-project : print
ms.assetid : 6a19c32c-62f2-4b88-908c-c6b92419e410
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : IPartFont, IPartFont::GetFontProperties, GetFontProperties
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
req.alt-api : IPartFont.GetFontProperties
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


# GetFontProperties method
The <b>GetFontProperties</b> method gets the font properties.

## Syntax

````
HRESULT GetFontProperties(
  [out] BSTR            *pContentType,
  [out] EXpsFontOptions *pFontOptions
);
````

## Parameters

`pContentType`

A pointer to the content type of the font.

`pFontOptions`

A pointer to the options of the font.


## Return Value

<b>GetFontProperties</b> returns an <b>HRESULT</b> value.


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