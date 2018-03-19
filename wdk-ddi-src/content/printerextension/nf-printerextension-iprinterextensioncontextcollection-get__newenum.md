---
UID: NF:printerextension.IPrinterExtensionContextCollection.get__NewEnum
title: IPrinterExtensionContextCollection::get__NewEnum method
author: windows-driver-content
description: Gets a pointer to the enumerants of IPrinterExtensionContextCollection objects.
old-location: print\iprinterextensioncontextcollection_newenum.htm
old-project: print
ms.assetid: 139B2E3F-AA08-4400-9BBF-A549B9EB2643
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterExtensionContextCollection, IPrinterExtensionContextCollection interface [Print Devices], NewEnum method, IPrinterExtensionContextCollection,get_NewEnum, NewEnum, IPrinterExtensionContextCollection::NewEnum, IPrinterExtensionContextCollection::get__NewEnum, NewEnum method [Print Devices], NewEnum method [Print Devices], IPrinterExtensionContextCollection interface, get__NewEnum,IPrinterExtensionContextCollection.get__NewEnum, print.iprinterextensioncontextcollection_newenum, printerextension/IPrinterExtensionContextCollection::NewEnum
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
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
-	IPrinterExtensionContextCollection.NewEnum
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# get__NewEnum method
Gets a pointer to the enumerants of <a href="..\printerextension\nn-printerextension-iprinterextensioncontextcollection.md">IPrinterExtensionContextCollection</a> objects.

## Syntax

````
HRESULT NewEnum(
  [out, retval] IUnknown **ppUnk
);
````

## Parameters

`ppUnk`




## Return Value

Returns an <b>HRESULT</b> value. If the property call was not successful,  it returns the appropriate <b>HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprinterextensioncontextcollection.md">IPrinterExtensionContextCollection</a>