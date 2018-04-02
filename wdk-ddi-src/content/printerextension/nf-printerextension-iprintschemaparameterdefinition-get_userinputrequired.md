---
UID: NF:printerextension.IPrintSchemaParameterDefinition.get_UserInputRequired
title: IPrintSchemaParameterDefinition::get_UserInputRequired method
author: windows-driver-content
description: The UserInputRequired property gets the Boolean value that indicates whether or not a user input value is required for the Print Schema parameter.
old-location: print\_iprintschemaparameterdefinition_userinputrequired.htm
old-project: print
ms.assetid: C2BA76C4-CCFB-4F0B-B5DC-3A35BD5A3884
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintSchemaParameterDefinition, IPrintSchemaParameterDefinition interface [Print Devices], UserInputRequired property, IPrintSchemaParameterDefinition.UserInputRequired, IPrintSchemaParameterDefinition::get_UserInputRequired, UserInputRequired property [Print Devices], UserInputRequired property [Print Devices], IPrintSchemaParameterDefinition interface, get_UserInputRequired, get_UserInputRequired,IPrintSchemaParameterDefinition.get_UserInputRequired, print._iprintschemaparameterdefinition_userinputrequired, printerextension/IPrintSchemaParameterDefinition::UserInputRequired, printerextension/IPrintSchemaParameterDefinition::get_UserInputRequired
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
-	IPrintSchemaParameterDefinition.UserInputRequired
-	IPrintSchemaParameterDefinition.get_UserInputRequired
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrintSchemaParameterDefinition::get_UserInputRequired method
The <b>UserInputRequired</b> property gets the Boolean value that indicates whether or not a user input value is required for the Print Schema parameter.

This property is read-only.

## Syntax

```
HRESULT get_UserInputRequired(
  BOOL *pbIsRequired
);
```

## Parameters

`pbIsRequired`




## Return Value

None

## Remarks

The print dialog can use <b>UserInputRequired</b> to determine whether or not it should force the user to enter a valid value for the parameter, before it allows printing to proceed.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn465890">IPrintSchemaParameterDefinition</a>