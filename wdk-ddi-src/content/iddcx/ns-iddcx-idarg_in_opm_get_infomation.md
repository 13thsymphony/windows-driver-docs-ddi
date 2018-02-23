---
UID: NS:iddcx.IDARG_IN_OPM_GET_INFOMATION
title: IDARG_IN_OPM_GET_INFOMATION
author: windows-driver-content
description: Gives information about the OPM.
old-location: display\idarg_in_opm_get_infomation.htm
old-project: display
ms.assetid: 14d0585d-6fa1-4934-a4f2-fe5e20d4a324
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.idarg_in_opm_get_infomation, iddcx/IDARG_IN_OPM_GET_INFOMATION, IDARG_IN_OPM_GET_INFOMATION, IDARG_IN_OPM_GET_INFOMATION structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iddcx.h
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
-	iddcx.h
apiname:
-	IDARG_IN_OPM_GET_INFOMATION
product: Windows
targetos: Windows
req.typenames: 
---

# IDARG_IN_OPM_GET_INFOMATION structure
Gives information about the OPM.

## Syntax
````
typedef struct IDARG_IN_OPM_GET_INFOMATION {
  IDDCX_OPM_GET_INFO_PARAMETERS GetInfoParameters;
} IDARG_IN_OPM_GET_INFOMATION, *IDARG_IN_OPM_GET_INFOMATION;
````

## Members


`GetInfoParameters`

[in] Parameters for the get information request


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iddcx.h |