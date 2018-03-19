---
UID: NF:filterpipeline.IXpsDocumentConsumer.GetNewEmptyPart
title: IXpsDocumentConsumer::GetNewEmptyPart method
author: windows-driver-content
description: The GetNewEmptyPart method creates a new XPS part.
old-location: print\ixpsdocumentconsumer_getnewemptypart.htm
old-project: print
ms.assetid: cc0911da-46ca-4cf7-a59e-da0d53e1d10c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetNewEmptyPart method [Print Devices], GetNewEmptyPart method [Print Devices], IXpsDocumentConsumer interface, GetNewEmptyPart,IXpsDocumentConsumer.GetNewEmptyPart, IXpsDocumentConsumer, IXpsDocumentConsumer interface [Print Devices], GetNewEmptyPart method, IXpsDocumentConsumer::GetNewEmptyPart, filterpipeline/IXpsDocumentConsumer::GetNewEmptyPart, filterpipeline_c4770528-f57a-4197-b60b-5b780d5e7752.xml, print.ixpsdocumentconsumer_getnewemptypart
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
-	IXpsDocumentConsumer.GetNewEmptyPart
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# GetNewEmptyPart method
The <code>GetNewEmptyPart</code> method creates a new XPS part.

## Syntax

````
HRESULT GetNewEmptyPart(
  [in]  const wchar_t           *uri,
  [in]        REFIID            riid,
  [out]       void              **ppNewObject,
  [out]       IPrintWriteStream **ppWriteStream
);
````

## Parameters

`uri`

The URI for the new part to be created.

`riid`

A reference identifier (REFIID) for one of the following interfaces: 

<ul>
<li>

<a href="..\filterpipeline\nn-filterpipeline-ifixeddocument.md">IFixedDocument</a>


</li>
<li>

<a href="..\filterpipeline\nn-filterpipeline-ifixedpage.md">IFixedPage</a>


</li>
<li>

<a href="..\filterpipeline\nn-filterpipeline-ipartimage.md">IPartImage</a>


</li>
<li>

<a href="..\filterpipeline\nn-filterpipeline-ipartthumbnail.md">IPartThumbnail</a>


</li>
<li>

<a href="..\filterpipeline\nn-filterpipeline-ipartfont.md">IPartFont</a>


</li>
<li>

<a href="..\filterpipeline\nn-filterpipeline-ipartprintticket.md">IPartPrintTicket</a>


</li>
<li>

<a href="..\filterpipeline\nn-filterpipeline-ipartcolorprofile.md">IPartColorProfile</a>


</li>
</ul>

`ppNewObject`

A pointer to the new object to be created.

`ppWriteStream`

A data stream object that the part will be written to. Each part is associated with a data stream object.


## Return Value

<code>GetNewEmptyPart</code> returns an <b>HRESULT</b>.

## Remarks

A filter can create new XPS parts by using the <code>GetNewEmptyPart</code> method. Typically, the filter receives XPS parts from the inter-filter object.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | filterpipeline.h |

## See Also

<a href="..\filterpipeline\nn-filterpipeline-ifixedpage.md">IFixedPage</a>



<a href="..\filterpipeline\nn-filterpipeline-ifixeddocument.md">IFixedDocument</a>



<a href="..\filterpipeline\nn-filterpipeline-ipartimage.md">IPartImage</a>



<a href="..\filterpipeline\nn-filterpipeline-ipartthumbnail.md">IPartThumbnail</a>



<a href="..\filterpipeline\nn-filterpipeline-ipartcolorprofile.md">IPartColorProfile</a>



<a href="..\filterpipeline\nn-filterpipeline-ixpsdocumentconsumer.md">IXpsDocumentConsumer</a>



<a href="..\filterpipeline\nn-filterpipeline-ipartfont.md">IPartFont</a>



<a href="..\filterpipeline\nn-filterpipeline-ipartprintticket.md">IPartPrintTicket</a>