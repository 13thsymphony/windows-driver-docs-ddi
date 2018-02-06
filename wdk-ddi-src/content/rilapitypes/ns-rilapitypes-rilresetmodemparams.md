---
UID: NS:rilapitypes.RILRESETMODEMPARAMS
title: RILRESETMODEMPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilresetmodemparams_2.htm
old-project: netvista
ms.assetid: 5888ba1d-b9f2-41c3-a39d-6a2fffc593fd
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILRESETMODEMPARAMS, RILRESETMODEMPARAMS structure [Network Drivers Starting with Windows Vista], rilapitypes/RILRESETMODEMPARAMS, netvista.rilresetmodemparams_2, *LPRILRESETMODEMPARAMS
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILRESETMODEMPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILRESETMODEMPARAMS, RILRESETMODEMPARAMS"
req.product: Windows 10 or later.
---

# RILRESETMODEMPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILRESETMODEMPARAMS {
  DWORD                       dwResetKind;
  DWORD                       dwNumberOfConfigItems;
  RILRESETMODEMCONFIGITEM [1] rmciModemConfigItems;
} RILRESETMODEMPARAMS, RILRESETMODEMPARAMS;
````

## Members


`dwNumberOfConfigItems`



`dwResetKind`



`rmciModemConfigItems`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |