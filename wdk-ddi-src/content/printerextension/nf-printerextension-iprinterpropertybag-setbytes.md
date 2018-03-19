---
UID: NF:printerextension.IPrinterPropertyBag.SetBytes
title: IPrinterPropertyBag::SetBytes method
author: windows-driver-content
description: Writes a byte array property.
old-location: print\iprinterpropertybag_setbytes.htm
old-project: print
ms.assetid: 0138F4F4-658F-4465-8647-17BE488E2FED
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterPropertyBag, IPrinterPropertyBag interface [Print Devices], SetBytes method, IPrinterPropertyBag::SetBytes, SetBytes method [Print Devices], SetBytes method [Print Devices], IPrinterPropertyBag interface, SetBytes,IPrinterPropertyBag.SetBytes, print.iprinterpropertybag_setbytes, printerextension/IPrinterPropertyBag::SetBytes
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
-	IPrinterPropertyBag.SetBytes
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# SetBytes method
Writes a byte array property.

## Syntax

````
HRESULT SetBytes(
  [in]                   BSTR   bstrName,
  [in]                   DWORD  cbValue,
  [in, size_is(cbValue)] BYTE * *rgbValue
);
````

## Parameters

`bstrName`

The array to write to.

`cbValue`

The number of bytes to write.

`pValue`




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

<a href="..\printerextension\nn-printerextension-iprinterpropertybag.md">IPrinterPropertyBag</a>