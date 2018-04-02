---
UID: NF:printerextension.IPrinterPropertyBag.GetInt32
title: IPrinterPropertyBag::GetInt32 method
author: windows-driver-content
description: Reads an integer property.
old-location: print\iprinterpropertybag_getint32.htm
old-project: print
ms.assetid: AFB73FA6-0979-4CED-8AB9-9D0FDD6C37E8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetInt32 method [Print Devices], GetInt32 method [Print Devices], IPrinterPropertyBag interface, GetInt32,IPrinterPropertyBag.GetInt32, IPrinterPropertyBag, IPrinterPropertyBag interface [Print Devices], GetInt32 method, IPrinterPropertyBag::GetInt32, print.iprinterpropertybag_getint32, printerextension/IPrinterPropertyBag::GetInt32
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
-	IPrinterPropertyBag.GetInt32
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrinterPropertyBag::GetInt32 method
Reads an integer property.

## Syntax

```
HRESULT GetInt32(
  BSTR bstrName,
  LONG *pnValue
);
```

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

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439547">IPrinterPropertyBag</a>