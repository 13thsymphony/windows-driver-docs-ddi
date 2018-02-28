---
UID: NS:rilapitypes.RILSENDRESTRICTEDUICCCMDPARAMS
title: RILSENDRESTRICTEDUICCCMDPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendrestricteduicccmdparams_2.htm
old-project: netvista
ms.assetid: f15bd639-0c58-45e1-91e4-dba25fac0686
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILSENDRESTRICTEDUICCCMDPARAMS, RILSENDRESTRICTEDUICCCMDPARAMS, RILSENDRESTRICTEDUICCCMDPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilsendrestricteduicccmdparams_2, rilapitypes/RILSENDRESTRICTEDUICCCMDPARAMS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
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
-	rilapitypes.h
api_name:
-	RILSENDRESTRICTEDUICCCMDPARAMS
product: Windows
targetos: Windows
req.typenames: RILSENDRESTRICTEDUICCCMDPARAMS, *LPRILSENDRESTRICTEDUICCCMDPARAMS
req.product: Windows 10 or later.
---

# RILSENDRESTRICTEDUICCCMDPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSENDRESTRICTEDUICCCMDPARAMS {
  DWORD                  cbSize;
  RILUICCCOMMAND         dwCommand;
  RILUICCCMDPARAMETERS   rscpParameters;
  BOOL                   fHasLockVerification;
  RILUICCLOCKCREDENTIAL  lockVerification;
  DWORD                  dwDataSize;
  BYTE [1]               pbData;
} RILSENDRESTRICTEDUICCCMDPARAMS, RILSENDRESTRICTEDUICCCMDPARAMS;
````

## Members


`cbSize`



`dwCommand`



`dwDataSize`



`fHasLockVerification`



`lockVerification`



`pbData`



`rscpParameters`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |