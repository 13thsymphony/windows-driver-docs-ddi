---
UID: NS:nfccx._NFCCX_DRIVER_GLOBALS
title: "_NFCCX_DRIVER_GLOBALS"
author: windows-driver-content
description: "."
old-location: nfpdrivers\nfccx_driver_globals.htm
old-project: nfpdrivers
ms.assetid: 3B84B227-7155-4FA2-A224-1317D103F5C3
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PNFCCX_DRIVER_GLOBALS, NFCCX_DRIVER_GLOBALS, NFCCX_DRIVER_GLOBALS structure [Near-Field Proximity Drivers], PNFCCX_DRIVER_GLOBALS, PNFCCX_DRIVER_GLOBALS structure pointer [Near-Field Proximity Drivers], _NFCCX_DRIVER_GLOBALS, nfccx/NFCCX_DRIVER_GLOBALS, nfccx/PNFCCX_DRIVER_GLOBALS, nfpdrivers.nfccx_driver_globals"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
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
-	nfccx.h
api_name:
-	NFCCX_DRIVER_GLOBALS
product: Windows
targetos: Windows
req.typenames: NFCCX_DRIVER_GLOBALS, *PNFCCX_DRIVER_GLOBALS
---

# _NFCCX_DRIVER_GLOBALS structure


## Syntax
````
typedef struct _NFCCX_DRIVER_GLOBALS {
  ULONG Reserved;
} NFCCX_DRIVER_GLOBALS, *PNFCCX_DRIVER_GLOBALS;
````

## Members


`Reserved`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | nfccx.h (include Ncidef.h) |

## See Also

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>