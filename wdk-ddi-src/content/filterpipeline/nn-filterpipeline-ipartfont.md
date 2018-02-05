---
UID : NN:filterpipeline.IPartFont
title : IPartFont
author : windows-driver-content
description : The IPartFont interface is the abstraction for fonts in a part.
old-location : print\ipartfont.htm
old-project : print
ms.assetid : bdb1ad56-de4c-4a9b-96b6-f9faff4abf65
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : print.ipartfont, IPartFont interface [Print Devices], IPartFont interface [Print Devices], described, IPartFont, filterpipeline/IPartFont, filterpipeline_def05492-ca27-43bb-9ec4-273aa432536b.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : interface
req.header : filterpipeline.h
req.include-header : Filterpipeline.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
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

# IPartFont interface

The <b>IPartFont</b> interface is the abstraction for fonts in a part.

## Methods

<p>The <b>IPartFont</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [filterpipeline.IPartFont.GetFontProperties](nf-filterpipeline-ipartfont-getfontproperties.md) | The GetFontProperties method gets the font properties. |
| [filterpipeline.IPartFont.SetFontContent](nf-filterpipeline-ipartfont-setfontcontent.md) | The SetFontContent method sets the content of the font. |
| [filterpipeline.IPartFont.SetFontOptions](nf-filterpipeline-ipartfont-setfontoptions.md) | The SetFontOptions method sets the options for the font. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | filterpipeline.h (include Filterpipeline.h) |

## See Also

<a href="..\filterpipeline\nn-filterpipeline-ipartbase.md">IPartBase</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPartFont interface%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>