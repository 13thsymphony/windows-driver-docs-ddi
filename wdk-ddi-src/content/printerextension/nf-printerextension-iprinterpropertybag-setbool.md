---
UID: NF:printerextension.IPrinterPropertyBag.SetBool
title: IPrinterPropertyBag::SetBool method
author: windows-driver-content
description: Writes a specified boolean property value.
old-location: print\iprinterpropertybag_setbool.htm
old-project: print
ms.assetid: B97C3FE9-0AC8-4147-A394-3344EBBA0B4C
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IPrinterPropertyBag, IPrinterPropertyBag interface [Print Devices], SetBool method, IPrinterPropertyBag::SetBool, SetBool method [Print Devices], SetBool method [Print Devices], IPrinterPropertyBag interface, SetBool,IPrinterPropertyBag.SetBool, print.iprinterpropertybag_setbool, printerextension/IPrinterPropertyBag::SetBool
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrinterPropertyBag.SetBool
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# SetBool method
Writes a specified boolean property value.

## Syntax

````
HRESULT SetBool(
  [in] BSTR bstrName,
  [in] BOOL bValue
);
````

## Parameters

`bstrName`

The property to set.

`bValue`

The value to set.


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
| **Library** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprinterpropertybag.md">IPrinterPropertyBag</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterPropertyBag::SetBool method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>