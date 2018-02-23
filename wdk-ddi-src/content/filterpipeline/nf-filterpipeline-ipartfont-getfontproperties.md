---
UID: NF:filterpipeline.IPartFont.GetFontProperties
title: IPartFont::GetFontProperties method
author: windows-driver-content
description: The GetFontProperties method gets the font properties.
old-location: print\ipartfont_getfontproperties.htm
old-project: print
ms.assetid: 6a19c32c-62f2-4b88-908c-c6b92419e410
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: filterpipeline_a84d2506-3e75-4dc9-ad3e-ef481bd2fd20.xml, print.ipartfont_getfontproperties, IPartFont interface [Print Devices], GetFontProperties method, GetFontProperties method [Print Devices], IPartFont interface, IPartFont::GetFontProperties, GetFontProperties method [Print Devices], filterpipeline/IPartFont::GetFontProperties, GetFontProperties, IPartFont
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
-	IPartFont.GetFontProperties
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
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
| **Target Platform** | Desktop |
| **Header** | filterpipeline.h |
| **Library** | filterpipeline.h |