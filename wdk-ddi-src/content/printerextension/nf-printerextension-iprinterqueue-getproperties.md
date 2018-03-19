---
UID: NF:printerextension.IPrinterQueue.GetProperties
title: IPrinterQueue::GetProperties method
author: windows-driver-content
description: Gets the properties in the property bag for the queue.
old-location: print\iprinterqueue_getproperties.htm
old-project: print
ms.assetid: 87EED8B5-676C-4056-812B-B0424148FCFA
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetProperties method [Print Devices], GetProperties method [Print Devices], IPrinterQueue interface, GetProperties,IPrinterQueue.GetProperties, IPrinterQueue, IPrinterQueue interface [Print Devices], GetProperties method, IPrinterQueue::GetProperties, print.iprinterqueue_getproperties, printerextension/IPrinterQueue::GetProperties
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
-	IPrinterQueue.GetProperties
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
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
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprinterpropertybag.md">IPrinterPropertyBag</a>



<a href="..\printerextension\nn-printerextension-iprinterqueue.md">IPrinterQueue</a>