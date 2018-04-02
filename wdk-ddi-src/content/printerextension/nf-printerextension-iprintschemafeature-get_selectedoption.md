---
UID: NF:printerextension.IPrintSchemaFeature.get_SelectedOption
title: IPrintSchemaFeature::get_SelectedOption method
author: windows-driver-content
description: Gets an IPrintSchemaOption representing the selected option.
old-location: print\iprintschemafeature_selectedoption.htm
old-project: print
ms.assetid: C22BC037-05D2-4F44-8704-D1D56909B603
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintSchemaFeature, IPrintSchemaFeature interface [Print Devices], SelectedOption property, IPrintSchemaFeature.SelectedOption, IPrintSchemaFeature::get_SelectedOption, SelectedOption property [Print Devices], SelectedOption property [Print Devices], IPrintSchemaFeature interface, get_SelectedOption, get_SelectedOption,IPrintSchemaFeature.get_SelectedOption, print.iprintschemafeature_selectedoption, printerextension/IPrintSchemaFeature::SelectedOption, printerextension/IPrintSchemaFeature::get_SelectedOption
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
-	IPrintSchemaFeature.SelectedOption
-	IPrintSchemaFeature.get_SelectedOption
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrintSchemaFeature::get_SelectedOption method
Gets an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451335">IPrintSchemaOption</a> representing the selected option.

This property is read-only.

## Syntax

```
HRESULT get_SelectedOption(
  IPrintSchemaOption **ppOption
);
```

## Parameters

`ppOption`




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



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451335">IPrintSchemaOption</a>



<a href="https://msdn.microsoft.com/5556BD5E-6489-4CCF-8C62-DDA53AD9F368">IPrintSchemaTicket_GetCapabilities</a>