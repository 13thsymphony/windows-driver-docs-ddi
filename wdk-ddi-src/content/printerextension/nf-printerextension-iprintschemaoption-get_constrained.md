---
UID: NF:printerextension.IPrintSchemaOption.get_Constrained
title: IPrintSchemaOption::get_Constrained method
author: windows-driver-content
description: Gets the constraint setting type for the schema option.
old-location: print\iprintschemaoption_constrained.htm
old-project: print
ms.assetid: 57E13395-9E23-4708-B4EC-6839CB6FC62B
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: IPrintSchemaOption, Constrained property [Print Devices], IPrintSchemaOption interface, IPrintSchemaOption interface [Print Devices], Constrained property, IPrintSchemaOption::get_Constrained, Constrained property [Print Devices], printerextension/IPrintSchemaOption::get_Constrained, get_Constrained, IPrintSchemaOption.Constrained, print.iprintschemaoption_constrained, printerextension/IPrintSchemaOption::Constrained
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
req.lib: printerextension.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Printerextension.h
apiname:
-	IPrintSchemaOption.Constrained
-	IPrintSchemaOption.get_Constrained
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# get_Constrained method
Gets  the constraint setting type for the schema option.

This property is read-only.

## Syntax

````
HRESULT get_Constrained(
  [out, retval] PrintSchemaConstrainedSetting *pSetting
);
````

## Parameters

`pSetting`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |
| **Library** | printerextension.h |

## See Also

<a href="..\printerextension\ne-printerextension-tagprintschemaconstrainedsetting.md">PrintSchemaConstrainedSetting</a>



<a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaOption::Constrained property%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>