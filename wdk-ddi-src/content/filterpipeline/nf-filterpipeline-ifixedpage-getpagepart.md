---
UID : NF:filterpipeline.IFixedPage.GetPagePart
title : IFixedPage::GetPagePart method
author : windows-driver-content
description : The GetPagePart method gets the images, thumbnails, fonts, and so on in a page by using the URI.
old-location : print\ifixedpage_getpagepart.htm
old-project : print
ms.assetid : 6ec8d282-eedb-419e-84cb-8f4776ea7650
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : print.ifixedpage_getpagepart, IFixedPage interface [Print Devices], GetPagePart method, IFixedPage::GetPagePart, filterpipeline_925ca634-7cac-41f6-b80f-cc5c90154ae0.xml, GetPagePart, GetPagePart method [Print Devices], GetPagePart method [Print Devices], IFixedPage interface, filterpipeline/IFixedPage::GetPagePart, IFixedPage
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
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : Filterpipeline.idl
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : filterpipeline.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : EXpsFontRestriction
---


# GetPagePart method
The <b>GetPagePart</b> method gets the images, thumbnails, fonts, and so on in a page by using the URI.

## Syntax

````
HRESULT GetPagePart(
  [in]  const wchar_t  *uri,
  [out]       IUnknown **ppUnk
);
````

## Parameters

`uri`

The URI for a part. For example, the filter might parse the page markup and find a referenced font. The filter can use the font URI in a call to <b>GetPagePart</b>. The filter could then retrieve the font object that is associated with the page.

`ppUnk`

The object that is to be queried.


## Return Value

<b>GetPagePart</b> returns an <b>HRESULT</b>.

## Remarks

A filter must use QueryInterface on the return value to see what part types reside in the page.

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