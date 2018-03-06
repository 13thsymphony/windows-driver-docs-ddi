---
UID: NF:printerextension.IPrinterExtensionContext.get_UserProperties
title: IPrinterExtensionContext::get_UserProperties method
author: windows-driver-content
description: Gets the user property bag for this app.
old-location: print\iprinterextensioncontext_userproperties.htm
old-project: print
ms.assetid: 21B370C9-BDF7-42A6-B0CC-BC9B19F9D2D5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterExtensionContext, IPrinterExtensionContext interface [Print Devices], UserProperties property, IPrinterExtensionContext.UserProperties, IPrinterExtensionContext::get_UserProperties, UserProperties property [Print Devices], UserProperties property [Print Devices], IPrinterExtensionContext interface, get_UserProperties, get_UserProperties,IPrinterExtensionContext.get_UserProperties, print.iprinterextensioncontext_userproperties, printerextension/IPrinterExtensionContext::UserProperties, printerextension/IPrinterExtensionContext::get_UserProperties
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: printerextension.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrinterExtensionContext.UserProperties
-	IPrinterExtensionContext.get_UserProperties
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# get_UserProperties method
Gets the user property bag for this app.

This property is read-only.

## Syntax

````
HRESULT get_UserProperties(
  [out, retval] IPrinterPropertyBag **ppPropertyBag
);
````

## Parameters

`ppPropertyBag`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |
| **Library** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprinterpropertybag.md">IPrinterPropertyBag</a>



<a href="..\printerextension\nn-printerextension-iprinterextensioncontext.md">IPrinterExtensionContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionContext::UserProperties property%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>