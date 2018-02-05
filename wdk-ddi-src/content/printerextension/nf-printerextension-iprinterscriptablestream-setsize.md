---
UID : NF:printerextension.IPrinterScriptableStream.SetSize
title : IPrinterScriptableStream::SetSize method
author : windows-driver-content
description : Sets the size of the scriptable stream, in bytes.
old-location : print\iprinterscriptablestream__setsize.htm
old-project : print
ms.assetid : 4A05474B-9856-48B0-9289-D87B8FF54B2F
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : SetSize method [Print Devices], IPrinterScriptableStream interface, IPrinterScriptableStream interface [Print Devices], SetSize method, print.iprinterscriptablestream__setsize, printerextension/IPrinterScriptableStream::SetSize, IPrinterScriptableStream, SetSize method [Print Devices], SetSize, IPrinterScriptableStream::SetSize
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


# SetSize method
Sets the size of the scriptable stream, in bytes.

## Syntax

````
HRESULT SetSize(
  [in] LONG lSize
);
````

## Parameters

`lSize`

The new size in bytes.


## Return Value

This method returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Desktop |
| **Header** | printerextension.h |
| **Library** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprinterscriptablestream.md">IPrinterScriptableStream</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterScriptableStream::SetSize method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>