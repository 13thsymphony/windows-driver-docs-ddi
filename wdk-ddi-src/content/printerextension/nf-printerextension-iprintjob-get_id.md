---
UID: NF:printerextension.IPrintJob.get_Id
title: IPrintJob::get_Id method
author: windows-driver-content
description: Gets the print job identifier (ID).
old-location: print\iprintjob_id.htm
old-project: print
ms.assetid: 8354E38C-0A3D-48CB-9CA5-0DC0C01FDF17
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintJob, IPrintJob interface [Print Devices], Id property, IPrintJob.Id, IPrintJob::get_Id, Id property [Print Devices], Id property [Print Devices], IPrintJob interface, get_Id, get_Id,IPrintJob.get_Id, print.iprintjob_id, printerextension/IPrintJob::Id, printerextension/IPrintJob::get_Id
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
-	IPrintJob.Id
-	IPrintJob.get_Id
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrintJob::get_Id method
Gets the print job identifier (ID).

This property is read-only.

## Syntax

```
HRESULT get_Id(
  ULONG *pulID
);
```

## Parameters

`pulID`




## Return Value

None

## Remarks

You must not use the <b>IPrintJob::Id</b> property  to invoke spooler Job APIs. This property is only provided as a way for you to identify a particular job, and to help with ordering or sorting of the jobs in the job snapshot.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265396">IPrintJob</a>