---
UID: NF:printerextension.IPrintSchemaCapabilities.get_JobCopiesAllDocumentsMaxValue
title: IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMaxValue method
author: windows-driver-content
description: Gets the JobCopiesAllDocuments parameter maximum value.
old-location: print\iprintschemacapabilities_get_jobcopiesalldocumentsmaxvalue.htm
old-project: print
ms.assetid: A0705B79-BD13-4AB7-8647-A7AF905B97CC
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintSchemaCapabilities, IPrintSchemaCapabilities interface [Print Devices], JobCopiesAllDocumentsMaxValue property, IPrintSchemaCapabilities.JobCopiesAllDocumentsMaxValue, IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMaxValue, JobCopiesAllDocumentsMaxValue property [Print Devices], JobCopiesAllDocumentsMaxValue property [Print Devices], IPrintSchemaCapabilities interface, get_JobCopiesAllDocumentsMaxValue, get_JobCopiesAllDocumentsMaxValue,IPrintSchemaCapabilities.get_JobCopiesAllDocumentsMaxValue, print.iprintschemacapabilities_get_jobcopiesalldocumentsmaxvalue, printerextension/IPrintSchemaCapabilities::JobCopiesAllDocumentsMaxValue, printerextension/IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMaxValue
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
-	IPrintSchemaCapabilities.JobCopiesAllDocumentsMaxValue
-	IPrintSchemaCapabilities.get_JobCopiesAllDocumentsMaxValue
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# get_JobCopiesAllDocumentsMaxValue method
Gets the <b>JobCopiesAllDocuments</b> parameter maximum value.

This is the copy count maximum.

This property is read-only.

## Syntax

````
HRESULT get_JobCopiesAllDocumentsMaxValue(
  [out, retval] ULONG *pulJobCopiesAllDocumentsMaxValue
);
````

## Parameters

`pulJobCopiesAllDocumentsMaxValue`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a>