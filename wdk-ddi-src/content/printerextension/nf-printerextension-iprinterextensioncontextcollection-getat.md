---
UID: NF:printerextension.IPrinterExtensionContextCollection.GetAt
title: IPrinterExtensionContextCollection::GetAt method
author: windows-driver-content
description: Gets a pointer to an IPrinterExtensionContext object.
old-location: print\iprinterextensioncontextcollection_getat.htm
old-project: print
ms.assetid: 5E3DC6C7-E370-4120-81B7-2093812AD009
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetAt method [Print Devices], GetAt method [Print Devices], IPrinterExtensionContextCollection interface, GetAt,IPrinterExtensionContextCollection.GetAt, IPrinterExtensionContextCollection, IPrinterExtensionContextCollection interface [Print Devices], GetAt method, IPrinterExtensionContextCollection::GetAt, get_GetAt, print.iprinterextensioncontextcollection_getat, printerextension/IPrinterExtensionContextCollection::GetAt
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
-	IPrinterExtensionContextCollection.GetAt
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# GetAt method
Gets a pointer to an <a href="..\printerextension\nn-printerextension-iprinterextensioncontext.md">IPrinterExtensionContext</a> object.

## Syntax

````
HRESULT GetAt(
  [in]          ULONG                    ulIndex,
  [out, retval] IPrinterExtensionContext **ppContext
);
````

## Parameters

`ulIndex`

The index of the <a href="..\printerextension\nn-printerextension-iprinterextensioncontext.md">IPrinterExtensionContext</a> object within the collection.

`ppContext`

Pointer to an <a href="..\printerextension\nn-printerextension-iprinterextensioncontext.md">IPrinterExtensionContext</a> interface.


## Return Value

This method returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprinterextensioncontextcollection.md">IPrinterExtensionContextCollection</a>



<a href="..\printerextension\nn-printerextension-iprinterextensioncontext.md">IPrinterExtensionContext</a>