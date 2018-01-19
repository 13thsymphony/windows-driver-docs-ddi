---
UID : NF:filterpipeline.IPartFont.SetFontOptions
title : IPartFont::SetFontOptions method
author : windows-driver-content
description : The SetFontOptions method sets the options for the font.
old-location : print\ipartfont_setfontoptions.htm
old-project : print
ms.assetid : 28c708b7-82bb-4246-bde8-88d471c8120c
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : IPartFont, IPartFont::SetFontOptions, SetFontOptions
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
req.alt-api : IPartFont.SetFontOptions
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


# SetFontOptions method
The <b>SetFontOptions</b> method sets the options for the font.

## Syntax

````
HRESULT SetFontOptions(
  [in] EXpsFontOptions options
);
````

## Parameters

`options`

An <a href="..\filterpipeline\ne-filterpipeline-__midl___midl_itf_filterpipeline_0000_0000_0002.md">ExpsFontOptions</a>-typed value that describes the options for the font.


## Return Value

<b>SetFontOptions</b> returns an <b>HRESULT</b> value.


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