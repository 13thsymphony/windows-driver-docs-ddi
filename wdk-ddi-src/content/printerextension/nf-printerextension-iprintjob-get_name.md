---
UID: NF:printerextension.IPrintJob.get_Name
title: IPrintJob::get_Name method
author: windows-driver-content
description: Gets the name of the print job.
old-location: print\iprintjob_name.htm
old-project: print
ms.assetid: E060EDA8-691F-4860-B422-24DFB7FCAFEF
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintJob, IPrintJob interface [Print Devices], Name property, IPrintJob.Name, IPrintJob::get_Name, Name property [Print Devices], Name property [Print Devices], IPrintJob interface, get_Name, get_Name,IPrintJob.get_Name, print.iprintjob_name, printerextension/IPrintJob::Name, printerextension/IPrintJob::get_Name
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
-	IPrintJob.Name
-	IPrintJob.get_Name
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrintJob::get_Name method
Gets the name of the print job.

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
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265396">IPrintJob</a>