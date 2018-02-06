---
UID: NS:winsplp.BranchOfficeJobDataPipelineFailed
title: BranchOfficeJobDataPipelineFailed
author: windows-driver-content
description: Contains the necessary data for logging a branch office job Pipeline Rendering Failed event on a remote server. This is based on standard job-related data available to the spooler.
old-location: print\branchofficejobdatapipelinefailed.htm
old-project: print
ms.assetid: 3F5DB2F5-40B6-4A8D-983C-065D17E62AE6
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PBranchOfficeJobDataPipelineFailed, *PBranchOfficeJobDataPipelineFailed, print.branchofficejobdatapipelinefailed, BranchOfficeJobDataPipelineFailed structure [Print Devices], winsplp/PBranchOfficeJobDataPipelineFailed, PBranchOfficeJobDataPipelineFailed structure pointer [Print Devices], BranchOfficeJobDataPipelineFailed, winsplp/BranchOfficeJobDataPipelineFailed
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winsplp.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Winsplp.h
apiname:
-	BranchOfficeJobDataPipelineFailed
product: Windows
targetos: Windows
req.typenames: "*PBranchOfficeJobDataPipelineFailed, BranchOfficeJobDataPipelineFailed"
req.product: Windows 10 or later.
---

# BranchOfficeJobDataPipelineFailed structure
Contains the necessary data for logging a branch office job Pipeline Rendering Failed event on a remote server. This is based on standard job-related data available to the spooler.

## Syntax
````
typedef struct {
  LPWSTR pDocumentName;
  LPWSTR pPrinterName;
  LPWSTR pExtraErrorInfo;
} BranchOfficeJobDataPipelineFailed, *PBranchOfficeJobDataPipelineFailed;
````

## Members


`pDocumentName`

Specifies the name of the print document.

`pExtraErrorInfo`

Specifies the name of the client machine printing the job.

`pPrinterName`

Specifies the print connection.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | winsplp.h |