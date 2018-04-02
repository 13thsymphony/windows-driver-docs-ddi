---
UID: NF:printerextension.IPrintSchemaCapabilities.get_JobCopiesAllDocumentsMinValue
title: IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMinValue method
author: windows-driver-content
description: Gets the JobCopiesAllDocuments parameter minimum value.
old-location: print\iprintschemacapabilities_jobcopiesalldocumentsminvalue.htm
old-project: print
ms.assetid: 181D085C-65C5-4D7E-9A1B-8641CC9B799B
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintSchemaCapabilities, IPrintSchemaCapabilities interface [Print Devices], JobCopiesAllDocumentsMinValue property, IPrintSchemaCapabilities.JobCopiesAllDocumentsMinValue, IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMinValue, JobCopiesAllDocumentsMinValue property [Print Devices], JobCopiesAllDocumentsMinValue property [Print Devices], IPrintSchemaCapabilities interface, get_JobCopiesAllDocumentsMinValue, get_JobCopiesAllDocumentsMinValue,IPrintSchemaCapabilities.get_JobCopiesAllDocumentsMinValue, print.iprintschemacapabilities_jobcopiesalldocumentsminvalue, printerextension/IPrintSchemaCapabilities::JobCopiesAllDocumentsMinValue, printerextension/IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMinValue
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
-	IPrintSchemaCapabilities.JobCopiesAllDocumentsMinValue
-	IPrintSchemaCapabilities.get_JobCopiesAllDocumentsMinValue
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMinValue method
Gets the <b>JobCopiesAllDocuments</b> parameter minimum value.

This is the copy count minimum.

This property is read-only.

## Syntax

```
HRESULT get_JobCopiesAllDocumentsMinValue(
  ULONG *pulJobCopiesAllDocumentsMinValue
);
```

## Parameters

`pulJobCopiesAllDocumentsMinValue`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451256">IPrintSchemaCapabilities</a>