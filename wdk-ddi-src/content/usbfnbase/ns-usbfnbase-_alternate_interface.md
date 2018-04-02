---
UID: NS:usbfnbase._ALTERNATE_INTERFACE
title: "_ALTERNATE_INTERFACE"
author: windows-driver-content
description: The ALTERNATE_INTERFACE structure provides information about alternate settings for a Universal Serial Bus (USB) interface.
old-location: buses\alternate_interface.htm
old-project: usbref
ms.assetid: F57FA113-F664-4B10-8457-DF6D266264E9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PALTERNATE_INTERFACE, ALTERNATE_INTERFACE, ALTERNATE_INTERFACE structure [Buses], PALTERNATE_INTERFACE, PALTERNATE_INTERFACE structure pointer [Buses], _ALTERNATE_INTERFACE, buses.alternate_interface, usbfnbase/ALTERNATE_INTERFACE, usbfnbase/PALTERNATE_INTERFACE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbfnbase.h
req.include-header: Usbfnbase.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbfnbase.h
api_name:
-	ALTERNATE_INTERFACE
product: Windows
targetos: Windows
req.typenames: ALTERNATE_INTERFACE, *PALTERNATE_INTERFACE
req.product: Windows 10 or later.
---

# _ALTERNATE_INTERFACE structure
The <b>ALTERNATE_INTERFACE</b> structure provides information about alternate settings for a Universal Serial Bus (USB) interface.

## Syntax
```
typedef struct _ALTERNATE_INTERFACE {
  USHORT InterfaceNumber;
  USHORT AlternateInterfaceNumber;
} ALTERNATE_INTERFACE, *PALTERNATE_INTERFACE;
```

## Members


`InterfaceNumber`

The index number for theUSB interface setting.

`AlternateInterfaceNumber`

The index number for the alternate USB interface setting.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbfnbase.h (include Usbfnbase.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt188001">USBFN_NOTIFICATION</a>