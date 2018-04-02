---
UID: NF:printerextension.IPrintSchemaFeature.get_SelectionType
title: IPrintSchemaFeature::get_SelectionType method
author: windows-driver-content
description: Gets the selection type of the Feature.
old-location: print\iprintschemafeature_selectiontype.htm
old-project: print
ms.assetid: FFFF05EF-CCD3-4298-A6DC-8FE998C53DEA
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintSchemaFeature, IPrintSchemaFeature interface [Print Devices], SelectionType property, IPrintSchemaFeature.SelectionType, IPrintSchemaFeature::get_SelectionType, SelectionType property [Print Devices], SelectionType property [Print Devices], IPrintSchemaFeature interface, get_SelectionType, get_SelectionType,IPrintSchemaFeature.get_SelectionType, print.iprintschemafeature_selectiontype, printerextension/IPrintSchemaFeature::SelectionType, printerextension/IPrintSchemaFeature::get_SelectionType
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
-	IPrintSchemaFeature.SelectionType
-	IPrintSchemaFeature.get_SelectionType
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrintSchemaFeature::get_SelectionType method
Gets the selection type of the Feature.

This property is read-only.

## Syntax

```
HRESULT get_SelectionType(
  PrintSchemaSelectionType *pSelectionType
);
```

## Parameters

`pSelectionType`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451284">IPrintSchemaFeature</a>