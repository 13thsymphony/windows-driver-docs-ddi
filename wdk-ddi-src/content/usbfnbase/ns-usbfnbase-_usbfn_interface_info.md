---
UID: NS:usbfnbase._USBFN_INTERFACE_INFO
title: "_USBFN_INTERFACE_INFO"
author: windows-driver-content
description: Describes an interface and its endpoints.
old-location: buses\usbfn_interface_info.htm
old-project: usbref
ms.assetid: 54647A9E-E0AB-4DE7-93FB-D0232D6AC646
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUSBFN_INTERFACE_INFO, PUSBFN_INTERFACE_INFO, PUSBFN_INTERFACE_INFO structure pointer [Buses], USBFN_INTERFACE_INFO, USBFN_INTERFACE_INFO structure [Buses], _USBFN_INTERFACE_INFO, buses.usbfn_interface_info, usbfnbase/PUSBFN_INTERFACE_INFO, usbfnbase/USBFN_INTERFACE_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbfnbase.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbfnbase.h
api_name:
-	USBFN_INTERFACE_INFO
product: Windows
targetos: Windows
req.typenames: USBFN_INTERFACE_INFO, *PUSBFN_INTERFACE_INFO
req.product: Windows 10 or later.
---

# _USBFN_INTERFACE_INFO structure
Describes an interface and its endpoints.

## Syntax
```
typedef struct _USBFN_INTERFACE_INFO {
  UINT8           InterfaceNumber;
  USBFN_BUS_SPEED Speed;
  USHORT          Size;
  UCHAR           InterfaceDescriptorSet[1];
} *PUSBFN_INTERFACE_INFO, USBFN_INTERFACE_INFO;
```

## Members


`InterfaceNumber`

The index number of the interface.

`Speed`

The operating bus speed indicated by <a href="https://msdn.microsoft.com/library/windows/hardware/mt187987">USBFN_BUS_SPEED</a>-typed flags.

`Size`

Specifies the total length, in bytes, of all data for the interface.

`InterfaceDescriptorSet`

Pointer to the first element in the array of that contains the interface descriptor set.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbfnbase.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt187987">USBFN_BUS_SPEED</a>