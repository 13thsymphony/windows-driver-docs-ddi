---
UID: NF:printerextension.IPrinterExtensionRequest.Complete
title: IPrinterExtensionRequest::Complete method
author: windows-driver-content
description: Completes the extension event.
old-location: print\iprinterextensionrequest_complete.htm
old-project: print
ms.assetid: 2182A3E0-6CFD-4B29-BE78-EE38CA630FA1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: Complete method [Print Devices], Complete method [Print Devices], IPrinterExtensionRequest interface, Complete,IPrinterExtensionRequest.Complete, IPrinterExtensionRequest, IPrinterExtensionRequest interface [Print Devices], Complete method, IPrinterExtensionRequest::Complete, print.iprinterextensionrequest_complete, printerextension/IPrinterExtensionRequest::Complete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
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
-	Printerextension.h
api_name:
-	IPrinterExtensionRequest.Complete
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# Complete method
Completes the extension event.

## Syntax

````
HRESULT Complete(
    Void
);
````

## Parameters

This function has no parameters.

## Return Value

This method returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8  |
| **Target Platform** | Desktop |
| **Header** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprinterextensionrequest.md">IPrinterExtensionRequest</a>