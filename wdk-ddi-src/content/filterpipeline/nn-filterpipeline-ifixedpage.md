---
UID: NN:filterpipeline.IFixedPage
title: IFixedPage
author: windows-driver-content
description: A filter uses the IFixedPage interface to work with fixed pages in an XPS document.
old-location: print\ifixedpage.htm
old-project: print
ms.assetid: e9e309ed-42e5-40cc-a230-6ca001f9fb1b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IFixedPage, IFixedPage interface [Print Devices], IFixedPage interface [Print Devices], described, filterpipeline/IFixedPage, filterpipeline_4070fd54-c1df-432a-b586-a93854bf7aee.xml, print.ifixedpage
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: filterpipeline.h
req.include-header: Filterpipeline.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
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
-	IFixedPage
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IFixedPage interface

A filter uses the <b>IFixedPage</b> interface to work with fixed pages in an XPS document.

## Methods

<p>The <b>IFixedPage</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [IFixedPage::DeleteResource](nf-filterpipeline-ifixedpage-deleteresource.md) | The DeleteResource method deletes a resource that is associated with the page. |
| [IFixedPage::GetPagePart](nf-filterpipeline-ifixedpage-getpagepart.md) | The GetPagePart method gets the images, thumbnails, fonts, and so on in a page by using the URI. |
| [IFixedPage::GetPrintTicket](nf-filterpipeline-ifixedpage-getprintticket.md) | The GetPrintTicket method gets the print ticket object for the fixed page. |
| [IFixedPage::GetWriteStream](nf-filterpipeline-ifixedpage-getwritestream.md) | The GetWriteStream method retrieves the stream object to write page markup to read . You can use this stream to change page markup. |
| [IFixedPage::GetXpsPartIterator](nf-filterpipeline-ifixedpage-getxpspartiterator.md) | The GetXpsPartIterator method gets an iterator to enumerate all of the parts that are associated with the page. |
| [IFixedPage::SetPagePart](nf-filterpipeline-ifixedpage-setpagepart.md) | The SetPagePart method associates a new part with the page. |
| [IFixedPage::SetPrintTicket](nf-filterpipeline-ifixedpage-setprintticket.md) | The SetPrintTicket method associates a print ticket with the page. |


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | filterpipeline.h (include Filterpipeline.h) |

## See Also

<a href="..\filterpipeline\nn-filterpipeline-ipartbase.md">IPartBase</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IFixedPage interface%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>