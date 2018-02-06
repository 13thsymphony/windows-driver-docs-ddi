---
UID: NF:printerextension.IPrinterPropertyBag.GetInt32
title: IPrinterPropertyBag::GetInt32 method
author: windows-driver-content
description: Reads an integer property.
old-location: print\iprinterpropertybag_getint32.htm
old-project: print
ms.assetid: AFB73FA6-0979-4CED-8AB9-9D0FDD6C37E8
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: printerextension/IPrinterPropertyBag::GetInt32, GetInt32 method [Print Devices], print.iprinterpropertybag_getint32, IPrinterPropertyBag interface [Print Devices], GetInt32 method, IPrinterPropertyBag::GetInt32, IPrinterPropertyBag, GetInt32 method [Print Devices], IPrinterPropertyBag interface, GetInt32
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: Printerextension.h
req.target-type: Desktop
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
req.lib: printerextension.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Printerextension.h
apiname:
-	IPrinterPropertyBag.GetInt32
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# GetInt32 method
Reads an integer property.

## Syntax

````
HRESULT GetInt32(
  [in]          BSTR bstrName,
  [out, retval] LONG *pnValue
);
````

## Parameters

`bstrName`

The property to read.

`pnValue`

The value read.


## Return Value

This method returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | printerextension.h (include Printerextension.h) |
| **Library** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprinterpropertybag.md">IPrinterPropertyBag</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterPropertyBag::GetInt32 method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>