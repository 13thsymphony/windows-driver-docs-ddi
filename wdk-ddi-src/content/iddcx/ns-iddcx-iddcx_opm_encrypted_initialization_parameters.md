---
UID: NS:iddcx.IDDCX_OPM_ENCRYPTED_INITIALIZATION_PARAMETERS
title: IDDCX_OPM_ENCRYPTED_INITIALIZATION_PARAMETERS
author: windows-driver-content
description: Gives information about the OPM encrypted initialization parameters.
old-location: display\iddcx_opm_encrypted_initialization_parameters.htm
old-project: display
ms.assetid: d1df3fc1-2d23-4e90-b663-6322ba4e1eff
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IDDCX_OPM_ENCRYPTED_INITIALIZATION_PARAMETERS, IDDCX_OPM_ENCRYPTED_INITIALIZATION_PARAMETERS structure [Display Devices], display.iddcx_opm_encrypted_initialization_parameters, iddcx/IDDCX_OPM_ENCRYPTED_INITIALIZATION_PARAMETERS
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iddcx.h
api_name:
-	IDDCX_OPM_ENCRYPTED_INITIALIZATION_PARAMETERS
product: Windows
targetos: Windows
req.typenames: 
---

# IDDCX_OPM_ENCRYPTED_INITIALIZATION_PARAMETERS structure
Gives information about the OPM encrypted initialization parameters.

## Syntax
````
typedef struct IDDCX_OPM_ENCRYPTED_INITIALIZATION_PARAMETERS {
  UINT                                    Size;
  OPM_ENCRYPTED_INITIALIZATION_PARAMETERS EncryptedParameters;
} IDDCX_OPM_ENCRYPTED_INITIALIZATION_PARAMETERS, *IDDCX_OPM_ENCRYPTED_INITIALIZATION_PARAMETERS;
````

## Members


`Size`

Total size of the structure.

`EncryptedParameters`

Initialization parameters.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iddcx.h |