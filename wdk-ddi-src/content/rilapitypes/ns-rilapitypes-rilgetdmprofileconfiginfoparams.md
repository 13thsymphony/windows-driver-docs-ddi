---
UID: NS:rilapitypes.RILGETDMPROFILECONFIGINFOPARAMS
title: RILGETDMPROFILECONFIGINFOPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetdmprofileconfiginfoparams_2.htm
old-project: netvista
ms.assetid: 9f9c4c27-0a32-40c6-a302-98b4013e2664
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILGETDMPROFILECONFIGINFOPARAMS, RILGETDMPROFILECONFIGINFOPARAMS, RILGETDMPROFILECONFIGINFOPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilgetdmprofileconfiginfoparams_2, rilapitypes/RILGETDMPROFILECONFIGINFOPARAMS"
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
-	RILGETDMPROFILECONFIGINFOPARAMS
product: Windows
targetos: Windows
req.typenames: RILGETDMPROFILECONFIGINFOPARAMS, *LPRILGETDMPROFILECONFIGINFOPARAMS
req.product: Windows 10 or later.
---

# RILGETDMPROFILECONFIGINFOPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILGETDMPROFILECONFIGINFOPARAMS {
  DWORD                dwExecutor;
  RILDMCONFIGINFOITEM  dwConfigItem;
} RILGETDMPROFILECONFIGINFOPARAMS, RILGETDMPROFILECONFIGINFOPARAMS;
````

## Members


`dwConfigItem`



`dwExecutor`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |