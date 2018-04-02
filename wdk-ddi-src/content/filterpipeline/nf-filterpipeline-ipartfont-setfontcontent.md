---
UID: NF:filterpipeline.IPartFont.SetFontContent
title: IPartFont::SetFontContent method
author: windows-driver-content
description: The SetFontContent method sets the content of the font.
old-location: print\ipartfont_setfontcontent.htm
old-project: print
ms.assetid: bd77d32f-97fd-4f80-945d-9fff7553fcc5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPartFont, IPartFont interface [Print Devices], SetFontContent method, IPartFont::SetFontContent, SetFontContent method [Print Devices], SetFontContent method [Print Devices], IPartFont interface, SetFontContent,IPartFont.SetFontContent, filterpipeline/IPartFont::SetFontContent, filterpipeline_1639cc2b-b1b6-4fa3-997b-3c98e32d2783.xml, print.ipartfont_setfontcontent
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
-	IPartFont.SetFontContent
product:
- Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# IPartFont::SetFontContent method
The <b>SetFontContent</b> method sets the content of the font.

## Syntax

```
HRESULT SetFontContent(
  const wchar_t *pContentType
);
```

## Parameters

`pContentType`




## Return Value

<b>SetFontContent</b> returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | filterpipeline.h |