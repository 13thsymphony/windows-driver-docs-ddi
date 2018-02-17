---
UID: NS:winsplp.BranchOfficeJobDataRendered
title: BranchOfficeJobDataRendered
author: windows-driver-content
description: Contains the necessary data for logging a branch office job Pipeline Rendering Event on a remote server. This is based on job-related data available to the spooler.
old-location: print\branchofficejobdatarendered.htm
old-project: print
ms.assetid: 67A296B3-5D59-475E-9026-EDAB90C8E3DD
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: "*PBranchOfficeJobDataRendered, winsplp/PBranchOfficeJobDataRendered, print.branchofficejobdatarendered, PBranchOfficeJobDataRendered structure pointer [Print Devices], BranchOfficeJobDataRendered, winsplp/BranchOfficeJobDataRendered, PBranchOfficeJobDataRendered, BranchOfficeJobDataRendered structure [Print Devices]"
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
-	BranchOfficeJobDataRendered
product: Windows
targetos: Windows
req.typenames: "*PBranchOfficeJobDataRendered, BranchOfficeJobDataRendered"
req.product: Windows 10 or later.
---

# BranchOfficeJobDataRendered structure
Contains the necessary data for logging a branch office job Pipeline Rendering Event on a remote server. This is based on job-related data available to the spooler.

## Syntax
````
typedef struct {
  LONGLONG Size;
  DWORD    ICMMethod;
  short    Color;
  short    PrintQuality;
  short    YResolution;
  short    Copies;
  short    TTOption;
} BranchOfficeJobDataRendered, *PBranchOfficeJobDataRendered;
````

## Members


`Color`

Describes the <b>short</b> type member <b>Color</b>.

`Copies`

Describes the <b>short</b> type member <b>Copies</b>.

`ICMMethod`

Describes the <b>DWORD</b> type member <b>ICMMethod</b>.

`PrintQuality`

Describes the <b>short</b> type member <b>PrintQuality</b>.

`Size`

Specifies the 64-bit size of the job.

`TTOption`

Describes the <b>short</b> type member <b>TTOption</b>.

`YResolution`

Describes the <b>short</b> type member <b>YResolution</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | winsplp.h |