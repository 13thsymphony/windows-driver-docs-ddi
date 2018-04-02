---
UID: NF:printerextension.IPrintSchemaElement.get_Name
title: IPrintSchemaElement::get_Name method
author: windows-driver-content
description: Gets the base value of the &#0034;name&#0034; attribute of this node.
old-location: print\iprintschemaelement_name.htm
old-project: print
ms.assetid: 025DC5A0-4462-487E-9C5B-0FE359DAD41C
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintSchemaElement, IPrintSchemaElement interface [Print Devices], Name property, IPrintSchemaElement.Name, IPrintSchemaElement::get_Name, Name property [Print Devices], Name property [Print Devices], IPrintSchemaElement interface, get_Name, get_Name,IPrintSchemaElement.get_Name, print.iprintschemaelement_name, printerextension/IPrintSchemaElement::Name, printerextension/IPrintSchemaElement::get_Name
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
-	IPrintSchemaElement.Name
-	IPrintSchemaElement.get_Name
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrintSchemaElement::get_Name method
Gets the base value of the "name" attribute of this node.

This property is read-only.

## Syntax

```
HRESULT get_Name(
  BSTR *pbstrName
);
```

## Parameters

`pbstrName`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451270">IPrintSchemaElement</a>