---
UID: NS:rilapitypes.RILUICCLOCKCREDENTIAL
title: RILUICCLOCKCREDENTIAL
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicclockcredential.htm
old-project: netvista
ms.assetid: 4ca8411e-2492-4832-881c-5fdb974485fc
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILUICCLOCKCREDENTIAL, RILUICCLOCKCREDENTIAL, RILUICCLOCKCREDENTIAL structure [Network Drivers Starting with Windows Vista], netvista.riluicclockcredential, ntddrilapitypes/RILUICCLOCKCREDENTIAL"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
-	ntddrilapitypes.h
api_name:
-	RILUICCLOCKCREDENTIAL
product: Windows
targetos: Windows
req.typenames: RILUICCLOCKCREDENTIAL, *LPRILUICCLOCKCREDENTIAL
req.product: Windows 10 or later.
---

# RILUICCLOCKCREDENTIAL structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILUICCLOCKCREDENTIAL {
  RILUICCLOCK  rilUiccLock;
  char [256]   szPassword;
} RILUICCLOCKCREDENTIAL, RILUICCLOCKCREDENTIAL;
````

## Members


`rilUiccLock`



`szPassword`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |