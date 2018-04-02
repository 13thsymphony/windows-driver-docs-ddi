---
UID: NF:printerextension.IPrintSchemaParameterDefinition.get_UnitType
title: IPrintSchemaParameterDefinition::get_UnitType method
author: windows-driver-content
description: The UnitType property gets the unit type.
old-location: print\_iprintschemaparameterdefinition_unittype.htm
old-project: print
ms.assetid: 7ED1D02B-07DB-409B-AABF-4ED1D28B3C43
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintSchemaParameterDefinition, IPrintSchemaParameterDefinition interface [Print Devices], UnitType property, IPrintSchemaParameterDefinition.UnitType, IPrintSchemaParameterDefinition::get_UnitType, UnitType property [Print Devices], UnitType property [Print Devices], IPrintSchemaParameterDefinition interface, get_UnitType, get_UnitType,IPrintSchemaParameterDefinition.get_UnitType, print._iprintschemaparameterdefinition_unittype, printerextension/IPrintSchemaParameterDefinition::UnitType, printerextension/IPrintSchemaParameterDefinition::get_UnitType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	IPrintSchemaParameterDefinition.UnitType
-	IPrintSchemaParameterDefinition.get_UnitType
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrintSchemaParameterDefinition::get_UnitType method
The <b>UnitType</b> property gets the unit type.

This property is read-only.

## Syntax

```
HRESULT get_UnitType(
  BSTR *pbstrUnitType
);
```

## Parameters

`pbstrUnitType`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn465890">IPrintSchemaParameterDefinition</a>