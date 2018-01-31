---
UID : NF:printerextension.IPrinterScriptablePropertyBag.GetInt32
title : IPrinterScriptablePropertyBag::GetInt32 method
author : windows-driver-content
description : Gets an integer property.
old-location : print\iprinterscriptablepropertybag_getint32.htm
old-project : print
ms.assetid : 0E1089E4-5FE4-4769-A244-3E1979E4DE46
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : printerextension/IPrinterScriptablePropertyBag::GetInt32, GetInt32 method [Print Devices], IPrinterScriptablePropertyBag interface [Print Devices], GetInt32 method, GetInt32, IPrinterScriptablePropertyBag::GetInt32, print.iprinterscriptablepropertybag_getint32, IPrinterScriptablePropertyBag, GetInt32 method [Print Devices], IPrinterScriptablePropertyBag interface
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : printerextension.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : printerextension.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PrintSchemaSelectionType
req.product : Windows 10 or later.
---


# GetInt32 method
Gets an integer property.

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

## Remarks

A call to <b>GetInt32</b> will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | printerextension.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\printerextension\nn-printerextension-iprinterscriptablepropertybag.md">IPrinterScriptablePropertyBag</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterScriptablePropertyBag::GetInt32 method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>