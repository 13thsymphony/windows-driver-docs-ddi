---
UID: NS:iddcx.IDARG_IN_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS
title: IDARG_IN_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS
author: windows-driver-content
description: Gives information about parameters necessary to set the signing key and sequence numbers.
old-location: display\idarg_in_opm_set_signing_key_and_sequence_numbers.htm
old-project: display
ms.assetid: 84b3f624-98bb-44b5-8050-8a12288cb827
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IDARG_IN_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS structure [Display Devices], display.idarg_in_opm_set_signing_key_and_sequence_numbers, IDARG_IN_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS, iddcx/IDARG_IN_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS
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
-	IDARG_IN_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS
product: Windows
targetos: Windows
req.typenames: 
---

# IDARG_IN_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS structure
Gives information about parameters necessary to set the signing key and sequence numbers.

## Syntax
````
typedef struct IDARG_IN_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS {
  IDDCX_OPM_ENCRYPTED_INITIALIZATION_PARAMETERS EncryptedParameters;
} IDARG_IN_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS, *IDARG_IN_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS;
````

## Members


`EncryptedParameters`

[in] Initialization parameters


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iddcx.h |