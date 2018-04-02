---
UID: NF:printerextension.IPrinterPropertyBag.GetBytes
title: IPrinterPropertyBag::GetBytes method
author: windows-driver-content
description: Reads a byte array property.
old-location: print\iprinterpropertybag_getbytes.htm
old-project: print
ms.assetid: F75E182D-90FA-4597-95E0-60A6326CF68D
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetBytes method [Print Devices], GetBytes method [Print Devices], IPrinterPropertyBag interface, GetBytes,IPrinterPropertyBag.GetBytes, IPrinterPropertyBag, IPrinterPropertyBag interface [Print Devices], GetBytes method, IPrinterPropertyBag::GetBytes, print.iprinterpropertybag_getbytes, printerextension/IPrinterPropertyBag::GetBytes
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
-	IPrinterPropertyBag.GetBytes
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrinterPropertyBag::GetBytes method
Reads a byte array property.

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439547">IPrinterPropertyBag</a> interface is used by all the printer property bags, including driver property bag, user property bag, queue property bag, and DEVMODE property bag.

## Syntax

```
HRESULT GetBytes(
  BSTR  bstrName,
  DWORD *pcbValue,
  BYTE  **ppValue
);
```

## Parameters

`bstrName`

The property to read.

`pcbValue`

The number of bytes read.

`ppValue`




## Return Value

This method returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | printerextension.h (include Printerextension.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439547">IPrinterPropertyBag</a>