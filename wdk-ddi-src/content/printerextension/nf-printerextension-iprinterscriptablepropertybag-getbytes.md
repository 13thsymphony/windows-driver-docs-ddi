---
UID : NF:printerextension.IPrinterScriptablePropertyBag.GetBytes
title : IPrinterScriptablePropertyBag::GetBytes method
author : windows-driver-content
description : Gets a byte array property.
old-location : print\iprinterscriptablepropertybag_getbytes.htm
old-project : print
ms.assetid : 419BCBB6-634A-421D-A940-8690BCCF1AC6
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : IPrinterScriptablePropertyBag::GetBytes, IPrinterScriptablePropertyBag interface [Print Devices], GetBytes method, GetBytes, GetBytes method [Print Devices], IPrinterScriptablePropertyBag, print.iprinterscriptablepropertybag_getbytes, GetBytes method [Print Devices], IPrinterScriptablePropertyBag interface, printerextension/IPrinterScriptablePropertyBag::GetBytes
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


# GetBytes method
Gets a byte array property.

## Syntax

````
HRESULT GetBytes(
  [in]          BSTR      bstrName,
  [out, retval] IDispatch **ppdispArray
);
````

## Parameters

`bstrName`

The property to read.

`ppArray`




## Return Value

This method returns an <b>HRESULT</b> value.

## Remarks

A call to <b>GetBytes</b> will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.

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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterScriptablePropertyBag::GetBytes method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>