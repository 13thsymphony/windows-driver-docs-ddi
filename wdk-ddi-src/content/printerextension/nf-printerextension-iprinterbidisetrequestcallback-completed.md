---
UID : NF:printerextension.IPrinterBidiSetRequestCallback.Completed
title : IPrinterBidiSetRequestCallback::Completed method
author : windows-driver-content
description : Invoked when the Bidi “Set”” operation is completed.
old-location : print\iprinterbidisetrequestcallback_completed.htm
old-project : print
ms.assetid : F086903F-2FCA-4B9F-948B-0F40F114E11D
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : Completed method [Print Devices], Completed, printerextension/IPrinterBidiSetRequestCallback::Completed, IPrinterBidiSetRequestCallback interface [Print Devices], Completed method, print.iprinterbidisetrequestcallback_completed, Completed method [Print Devices], IPrinterBidiSetRequestCallback interface, IPrinterBidiSetRequestCallback::Completed, IPrinterBidiSetRequestCallback
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : printerextension.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : Windows Server 2012 R2
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


# Completed method
Invoked when the Bidi “Set”” operation is completed.

## Syntax

````
HRESULT Completed(
  [in] BSTR    bstrResponse,
  [in] HRESULT hrStatus
);
````

## Parameters

`bstrResponse`

The received response.

`hrStatus`

An HRESULT value.


## Return Value

This method returns the appropriate <b>HRESULT</b> value.


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

<a href="..\printerextension\nn-printerextension-iprinterbidisetrequestcallback.md">IPrinterBidiSetRequestCallback</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterBidiSetRequestCallback::Completed method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>