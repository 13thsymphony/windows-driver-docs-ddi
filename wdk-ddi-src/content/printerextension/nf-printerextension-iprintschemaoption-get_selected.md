---
UID: NF:printerextension.IPrintSchemaOption.get_Selected
title: IPrintSchemaOption::get_Selected method
author: windows-driver-content
description: Indicates whether this option is selected.
old-location: print\iprintschemaoption_selected.htm
old-project: print
ms.assetid: 639D25DC-027F-4B53-AD7B-B26011B66171
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintSchemaOption, IPrintSchemaOption interface [Print Devices], Selected property, IPrintSchemaOption.Selected, IPrintSchemaOption::get_Selected, Selected property [Print Devices], Selected property [Print Devices], IPrintSchemaOption interface, get_Selected, get_Selected,IPrintSchemaOption.get_Selected, print.iprintschemaoption_selected, printerextension/IPrintSchemaOption::Selected, printerextension/IPrintSchemaOption::get_Selected
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
-	IPrintSchemaOption.Selected
-	IPrintSchemaOption.get_Selected
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrintSchemaOption::get_Selected method
Indicates whether this option is selected.

This property is read-only.

## Syntax

```
HRESULT get_Selected(
  BOOL *pbIsSelected
);
```

## Parameters

`pbIsSelected`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451335">IPrintSchemaOption</a>