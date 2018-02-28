---
UID: NF:printerextension.IPrinterExtensionEventArgs.get_BidiNotification
title: IPrinterExtensionEventArgs::get_BidiNotification method
author: windows-driver-content
description: Gets the text of the bidirectional communication (Bidi) notification, if applicable.
old-location: print\iprinterextensioneventargs_bidinotification.htm
old-project: print
ms.assetid: 8AAC657A-218E-41CF-AE89-0199A5B35280
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: BidiNotification property [Print Devices], BidiNotification property [Print Devices], IPrinterExtensionEventArgs interface, IPrinterExtensionEventArgs, IPrinterExtensionEventArgs interface [Print Devices], BidiNotification property, IPrinterExtensionEventArgs.BidiNotification, IPrinterExtensionEventArgs::get_BidiNotification, get_BidiNotification, get_BidiNotification,IPrinterExtensionEventArgs.get_BidiNotification, print.iprinterextensioneventargs_bidinotification, printerextension/IPrinterExtensionEventArgs::BidiNotification, printerextension/IPrinterExtensionEventArgs::get_BidiNotification
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
-	IPrinterExtensionEventArgs.BidiNotification
-	IPrinterExtensionEventArgs.get_BidiNotification
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# get_BidiNotification method
Gets the text of the bidirectional communication (Bidi) notification, if applicable.

This property is read-only.

## Syntax

````
HRESULT get_BidiNotification(
  [out, retval] BSTR *pbstrBidiNotification
);
````

## Parameters

`pbstrBidiNotification`




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

<a href="..\printerextension\nn-printerextension-iprinterextensioneventargs.md">IPrinterExtensionEventArgs</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionEventArgs::BidiNotification property%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>