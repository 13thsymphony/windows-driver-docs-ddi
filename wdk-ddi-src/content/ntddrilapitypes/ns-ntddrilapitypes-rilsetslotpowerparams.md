---
UID: NS:ntddrilapitypes.RILSETSLOTPOWERPARAMS
title: RILSETSLOTPOWERPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetslotpowerparams.htm
old-project: netvista
ms.assetid: 3e3bd3f1-08a2-4b20-b427-85b1236325b9
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILSETSLOTPOWERPARAMS, *LPRILSETSLOTPOWERPARAMS, ntddrilapitypes/RILSETSLOTPOWERPARAMS, netvista.rilsetslotpowerparams, RILSETSLOTPOWERPARAMS structure [Network Drivers Starting with Windows Vista]
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
-	RILSETSLOTPOWERPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILSETSLOTPOWERPARAMS, RILSETSLOTPOWERPARAMS"
---

# RILSETSLOTPOWERPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSETSLOTPOWERPARAMS {
  DWORD  dwSlotIndex;
  BOOL   fPowerOn;
} RILSETSLOTPOWERPARAMS, RILSETSLOTPOWERPARAMS;
````

## Members


`dwSlotIndex`



`fPowerOn`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |