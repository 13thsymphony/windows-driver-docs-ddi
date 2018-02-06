---
UID: NN:filterpipeline.IPartImage
title: IPartImage
author: windows-driver-content
description: The IPartImage interface is the abstraction for images in an XPS document.
old-location: print\ipartimage.htm
old-project: print
ms.assetid: 7bb39a5b-7519-47a6-82ca-440942ae2c84
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print.ipartimage, IPartImage interface [Print Devices], IPartImage interface [Print Devices], described, IPartImage, filterpipeline/IPartImage, filterpipeline_faed49d4-60d1-4063-a4aa-c9ec8c56655d.xml
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
-	IPartImage
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IPartImage interface

The <b>IPartImage</b> interface is the abstraction for images in an XPS document.

## Methods

<p>The <b>IPartImage</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [filterpipeline.IPartImage.GetImageProperties](nf-filterpipeline-ipartimage-getimageproperties.md) | The GetImageProperties method gets an image property that is based on the content type. |
| [filterpipeline.IPartImage.SetImageContent](nf-filterpipeline-ipartimage-setimagecontent.md) | The SetImageContent method sets an image property that is based on the content type. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | filterpipeline.h (include Filterpipeline.h) |

## See Also

<a href="..\filterpipeline\nn-filterpipeline-ipartbase.md">IPartBase</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPartImage interface%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>