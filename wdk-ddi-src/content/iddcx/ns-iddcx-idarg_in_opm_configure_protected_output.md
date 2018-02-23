---
UID: NS:iddcx.IDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT
title: IDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT
author: windows-driver-content
description: Gives information about the buffer that the driver will copy configuration parameters to.
old-location: display\idarg_in_opm_configure_protected_output.htm
old-project: display
ms.assetid: 523b904c-c833-40f2-8173-7ec1c6687b26
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: IDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT structure [Display Devices], IDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT, iddcx/IDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT, display.idarg_in_opm_configure_protected_output
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
-	IDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT
product: Windows
targetos: Windows
req.typenames: 
---

# IDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT structure
Gives information about the buffer that the driver will copy configuration parameters to.

## Syntax
````
typedef struct IDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT {
  IDDCX_OPM_CONFIGURE_PARAMETERS                           ConfigParameters;
  UINT                                                     AdditionalParametersSizeInBytes;
  _Field_size_full_(AdditionalParametersSizeInBytes) PVOID pAdditionalParameters;
} IDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT, *IDARG_IN_OPM_CONFIGURE_PROTECTED_OUTPUT;
````

## Members


`AdditionalParametersSizeInBytes`

[in] Size of additional parameter buffer

`ConfigParameters`

[in] Configuration parameters

`pAdditionalParameters`

[in] A pointer to a buffer that the driver copies the configuration info to.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iddcx.h |