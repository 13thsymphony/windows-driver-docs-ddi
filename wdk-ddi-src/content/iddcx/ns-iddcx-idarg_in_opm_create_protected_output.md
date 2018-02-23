---
UID: NS:iddcx.IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT
title: IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT
author: windows-driver-content
description: Gives information about the video output semantics for the OPM context that will be created.
old-location: display\idarg_in_opm_create_protected_output.htm
old-project: display
ms.assetid: c5727881-de35-4a61-bf54-0552d2de454b
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.idarg_in_opm_create_protected_output, IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT structure [Display Devices], IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT, iddcx/IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT
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
-	IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT
product: Windows
targetos: Windows
req.typenames: 
---

# IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT structure
Gives information about the video output semantics for the OPM  context that will be created.

## Syntax
````
typedef struct IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT {
  OPM_VIDEO_OUTPUT_SEMANTICS VideoOutputSemantics;
} IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT, *IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT;
````

## Members


`VideoOutputSemantics`

[in] Type of video output semantics used for this context.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iddcx.h |