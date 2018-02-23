---
UID: NS:ntddrilapitypes.RILGETDEVICEINFOPARAMS
title: RILGETDEVICEINFOPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetdeviceinfoparams.htm
old-project: netvista
ms.assetid: 4cb3be01-7e74-4c98-9c4b-2e1c78d96001
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILGETDEVICEINFOPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilgetdeviceinfoparams, RILGETDEVICEINFOPARAMS, *LPRILGETDEVICEINFOPARAMS, ntddrilapitypes/RILGETDEVICEINFOPARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
-	ntddrilapitypes.h
apiname:
-	RILGETDEVICEINFOPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILGETDEVICEINFOPARAMS, RILGETDEVICEINFOPARAMS"
---

# RILGETDEVICEINFOPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILGETDEVICEINFOPARAMS {
  DWORD                 dwExecutor;
  RILDEVICEINFORMATION  dwId;
} RILGETDEVICEINFOPARAMS, RILGETDEVICEINFOPARAMS;
````

## Members


`dwExecutor`



`dwId`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |