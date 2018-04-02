---
UID: NF:printerextension.IPrinterPropertyBag.SetInt32
title: IPrinterPropertyBag::SetInt32 method
author: windows-driver-content
description: Writes an integer property.
old-location: print\iprinterpropertybag_setint32.htm
old-project: print
ms.assetid: 9E6B55C3-C177-4C07-9AB5-7C743CE47016
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterPropertyBag, IPrinterPropertyBag interface [Print Devices], SetInt32 method, IPrinterPropertyBag::SetInt32, SetInt32 method [Print Devices], SetInt32 method [Print Devices], IPrinterPropertyBag interface, SetInt32,IPrinterPropertyBag.SetInt32, print.iprinterpropertybag_setint32, printerextension/IPrinterPropertyBag::SetInt32
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
-	IPrinterPropertyBag.SetInt32
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrinterPropertyBag::SetInt32 method
Writes an integer property.

## Syntax

```
HRESULT SetInt32(
  BSTR bstrName,
  LONG nValue
);
```

## Parameters

`bstrName`

The property to set.

`nValue`

The new value to set.


## Return Value

This method returns an <b>HRESULT</b> value.

## Remarks

In Windows 8.1 a new flag, PRINTER_ACCESS_MANAGE_LIMITED, has been introduced to grant print queue permissions that are more limited than PRINTER_ACCESS_ADMINISTER, but more powerful than 
PRINTER_ACCESS_USE.

The permissions are a subset of those associated with PRINTER_ACCESS_ADMINISTER. This means that if the currently logged-on user has PRINTER_ACCESS_ADMINISTER permission, the user can gain 
PRINTER_ACCESS_MANAGE_LIMITED access to the queue.

A call to set a property on a queue property bag will fail with ERROR_ACCESS_DENIED, if the user does not have the appropriate permission. This behavior was true before PRINTER_ACCESS_MANAGE_LIMITED was introduced, and it's still the current behavior.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | printerextension.h (include Printerextension.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439547">IPrinterPropertyBag</a>