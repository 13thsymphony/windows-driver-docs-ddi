---
UID : NF:printerextension.IPrinterQueue.GetProperties
title : IPrinterQueue::GetProperties method
author : windows-driver-content
description : Gets the properties in the property bag for the queue.
old-location : print\iprinterqueue_getproperties.htm
old-project : print
ms.assetid : 87EED8B5-676C-4056-812B-B0424148FCFA
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : IPrinterQueue::GetProperties, IPrinterQueue, GetProperties, printerextension/IPrinterQueue::GetProperties, print.iprinterqueue_getproperties, GetProperties method [Print Devices], IPrinterQueue interface [Print Devices], GetProperties method, GetProperties method [Print Devices], IPrinterQueue interface
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


# GetProperties method
Gets the properties in the property bag for the queue.

## Syntax

````
HRESULT GetProperties(
  [out, retval] IPrinterPropertyBag **ppPropertyBag
);
````

## Parameters

`ppPropertyBag`

A pointer to the property bag.


## Return Value

This method returns and <b>HRESULT</b> value.


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

<a href="..\printerextension\nn-printerextension-iprinterqueue.md">IPrinterQueue</a>

<a href="..\printerextension\nn-printerextension-iprinterpropertybag.md">IPrinterPropertyBag</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterQueue::GetProperties method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>