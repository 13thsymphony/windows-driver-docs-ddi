---
UID: NS:ntddrilapitypes.RILSETDMPROFILECONFIGINFOPARAMS
title: RILSETDMPROFILECONFIGINFOPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetdmprofileconfiginfoparams.htm
old-project: netvista
ms.assetid: d485f00e-5fa6-4a01-83fe-78e59a8d8fcb
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILSETDMPROFILECONFIGINFOPARAMS structure [Network Drivers Starting with Windows Vista], RILSETDMPROFILECONFIGINFOPARAMS, ntddrilapitypes/RILSETDMPROFILECONFIGINFOPARAMS, *LPRILSETDMPROFILECONFIGINFOPARAMS, netvista.rilsetdmprofileconfiginfoparams
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
-	RILSETDMPROFILECONFIGINFOPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILSETDMPROFILECONFIGINFOPARAMS, RILSETDMPROFILECONFIGINFOPARAMS"
---

# RILSETDMPROFILECONFIGINFOPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSETDMPROFILECONFIGINFOPARAMS {
  DWORD                 dwExecutor;
  RILDMCONFIGINFOITEM   dwConfigItem;
  RILDMCONFIGINFOVALUE  rciValue;
} RILSETDMPROFILECONFIGINFOPARAMS, RILSETDMPROFILECONFIGINFOPARAMS;
````

## Members


`dwConfigItem`



`dwExecutor`



`rciValue`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |