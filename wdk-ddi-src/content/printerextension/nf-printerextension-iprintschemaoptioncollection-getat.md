---
UID: NF:printerextension.IPrintSchemaOptionCollection.GetAt
title: IPrintSchemaOptionCollection::GetAt method
author: windows-driver-content
description: Gets a pointer to an IPrintSchemaOption object.
old-location: print\iprintschemaoptioncollection_getat.htm
old-project: print
ms.assetid: B77297BF-09F7-46BD-A75F-D36E5E233E05
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetAt method [Print Devices], GetAt method [Print Devices], IPrintSchemaOptionCollection interface, GetAt,IPrintSchemaOptionCollection.GetAt, IPrintSchemaOptionCollection, IPrintSchemaOptionCollection interface [Print Devices], GetAt method, IPrintSchemaOptionCollection::GetAt, print.iprintschemaoptioncollection_getat, printerextension/IPrintSchemaOptionCollection::GetAt
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
-	IPrintSchemaOptionCollection.GetAt
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrintSchemaOptionCollection::GetAt method
Gets a pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451335">IPrintSchemaOption</a> object.

## Syntax

```
HRESULT GetAt(
  ULONG              ulIndex,
  IPrintSchemaOption **ppOption
);
```

## Parameters

`ulIndex`

Index of the <b>IPrintSchemaOption</b> object within the collection.

`ppOption`

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451335">IPrintSchemaOption</a> object.


## Return Value

Returns an <b>HRESULT</b> value. If the method call was not successful,  it returns the appropriate <b>HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451335">IPrintSchemaOption</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh846198">IPrintSchemaOptionCollection</a>