---
UID: NF:printerextension.IPrintJob.get_SubmissionTime
title: IPrintJob::get_SubmissionTime method
author: windows-driver-content
description: Gets the submission time, in the “DATE” format, provided in the user’s local time (not in the UTC format that is provided by the spooler).
old-location: print\iprintjob_submissiontime.htm
old-project: print
ms.assetid: 23433B59-A376-4D92-863E-4492621F3BF5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintJob, IPrintJob interface [Print Devices], SubmissionTime property, IPrintJob.SubmissionTime, IPrintJob::get_SubmissionTime, SubmissionTime property [Print Devices], SubmissionTime property [Print Devices], IPrintJob interface, get_SubmissionTime, get_SubmissionTime,IPrintJob.get_SubmissionTime, print.iprintjob_submissiontime, printerextension/IPrintJob::SubmissionTime, printerextension/IPrintJob::get_SubmissionTime
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
-	IPrintJob.SubmissionTime
-	IPrintJob.get_SubmissionTime
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# get_SubmissionTime method
Gets the submission time, in the “DATE” format, provided in the user’s local time (not in the UTC format that is provided by the spooler).

This property is read-only.

## Syntax

````
HRESULT get_SubmissionTime(
  [out, retval] DATE *pSubmissionTime
);
````

## Parameters

`pSubmissionTime`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprintjob.md">IPrintJob</a>