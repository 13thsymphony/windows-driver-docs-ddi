---
UID: NF:printerextension.IPrinterScriptablePropertyBag.SetString
title: IPrinterScriptablePropertyBag::SetString method
author: windows-driver-content
description: Writes a string property.
old-location: print\iprinterscriptablepropertybag_setstring.htm
old-project: print
ms.assetid: 9B4EBCA4-8370-4F00-9853-6EE8408367BE
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IPrinterScriptablePropertyBag, IPrinterScriptablePropertyBag interface [Print Devices], SetString method, IPrinterScriptablePropertyBag::SetString, SetString method [Print Devices], SetString method [Print Devices], IPrinterScriptablePropertyBag interface, SetString,IPrinterScriptablePropertyBag.SetString, print.iprinterscriptablepropertybag_setstring, printerextension/IPrinterScriptablePropertyBag::SetString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
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
-	IPrinterScriptablePropertyBag.SetString
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# SetString method
Writes a string property.

## Syntax

````
HRESULT SetString(
  [in] BSTR bstrName,
  [in] BSTR bstrValue
);
````

## Parameters

`bstrName`

The property to set.

`bstrValue`

The property value to set.


## Return Value

This method returns an <b>HRESULT</b> value.

## Remarks

A call to <b>SetString</b> will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | printerextension.h |
| **Library** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprinterscriptablepropertybag.md">IPrinterScriptablePropertyBag</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterScriptablePropertyBag::SetString method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>