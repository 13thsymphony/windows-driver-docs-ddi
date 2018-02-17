---
UID: NS:iddcx.IDD_DRIVER_GLOBALS
title: IDD_DRIVER_GLOBALS
author: windows-driver-content
description: Holds per-driver Indirect Display information. Reserved for use by the system.
old-location: display\idd_driver_globals.htm
old-project: display
ms.assetid: 77d2c668-21e4-4c6d-9f3d-7e34c660d1da
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: iddcx/IDD_DRIVER_GLOBALS, display.idd_driver_globals, IDD_DRIVER_GLOBALS structure [Display Devices], IDD_DRIVER_GLOBALS, *PIDD_DRIVER_GLOBALS
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
-	IDD_DRIVER_GLOBALS
product: Windows
targetos: Windows
req.typenames: IDD_DRIVER_GLOBALS, *PIDD_DRIVER_GLOBALS
---

# IDD_DRIVER_GLOBALS structure
Holds per-driver Indirect Display information. Reserved for use by the system.

## Syntax
````
typedef struct IDD_DRIVER_GLOBALS {
  ULONG Reserved;
} IDD_DRIVER_GLOBALS, *IDD_DRIVER_GLOBALS;
````

## Members


`Reserved`

This value is reserved for use by the system.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iddcx.h |