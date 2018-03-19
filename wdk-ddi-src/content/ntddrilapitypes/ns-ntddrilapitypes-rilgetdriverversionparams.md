---
UID: NS:ntddrilapitypes.RILGETDRIVERVERSIONPARAMS
title: RILGETDRIVERVERSIONPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetdriverversionparams.htm
old-project: netvista
ms.assetid: 42167f2f-0bd5-452c-9b41-d18efac28a33
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILGETDRIVERVERSIONPARAMS, RILGETDRIVERVERSIONPARAMS, RILGETDRIVERVERSIONPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilgetdriverversionparams, ntddrilapitypes/RILGETDRIVERVERSIONPARAMS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
-	RILGETDRIVERVERSIONPARAMS
product: Windows
targetos: Windows
req.typenames: RILGETDRIVERVERSIONPARAMS, *LPRILGETDRIVERVERSIONPARAMS
---

# RILGETDRIVERVERSIONPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILGETDRIVERVERSIONPARAMS {
  DWORD  dwMinVersion;
  DWORD  dwMaxVersion;
} RILGETDRIVERVERSIONPARAMS, RILGETDRIVERVERSIONPARAMS;
````

## Members


`dwMinVersion`



`dwMaxVersion`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |