---
UID: NF:printerextension.IPrinterExtensionContext.get_PrinterQueue
title: IPrinterExtensionContext::get_PrinterQueue method
author: windows-driver-content
description: Gets the queue for the printer.
old-location: print\iprinterextensioncontext_printerqueue.htm
old-project: print
ms.assetid: 304C8AF5-EA4E-4401-A8EC-6E1B279038E8
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IPrinterExtensionContext, IPrinterExtensionContext interface [Print Devices], PrinterQueue property, IPrinterExtensionContext.PrinterQueue, IPrinterExtensionContext::get_PrinterQueue, PrinterQueue property [Print Devices], PrinterQueue property [Print Devices], IPrinterExtensionContext interface, get_PrinterQueue, get_PrinterQueue,IPrinterExtensionContext.get_PrinterQueue, print.iprinterextensioncontext_printerqueue, printerextension/IPrinterExtensionContext::PrinterQueue, printerextension/IPrinterExtensionContext::get_PrinterQueue
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
-	IPrinterExtensionContext.PrinterQueue
-	IPrinterExtensionContext.get_PrinterQueue
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# get_PrinterQueue method
Gets the queue for the printer.

This property is read-only.

## Syntax

````
HRESULT get_PrinterQueue(
  [out, retval] IPrinterQueue **ppQueue
);
````

## Parameters

`ppQueue`




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

<a href="..\printerextension\nn-printerextension-iprinterqueue.md">IPrinterQueue</a>



<a href="..\printerextension\nn-printerextension-iprinterextensioncontext.md">IPrinterExtensionContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionContext::PrinterQueue property%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>