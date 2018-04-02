---
UID: NS:ucxusbdevice._UCXUSBDEVICE_INFO
title: "_UCXUSBDEVICE_INFO"
author: windows-driver-content
description: Contains information about the USB device. This structure is passed by UCX in the EVT_UCX_CONTROLLER_USBDEVICE_ADD event callback function.
old-location: buses\_ucxusbdevice_info.htm
old-project: usbref
ms.assetid: E6875195-D6C4-4CEB-8381-8CBA732223A5
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUCXUSBDEVICE_INFO, P_UCXUSBDEVICE_INFO, P_UCXUSBDEVICE_INFO structure pointer [Buses], UCXUSBDEVICE_INFO, UCXUSBDEVICE_INFO structure [Buses], _UCXUSBDEVICE_INFO, buses._ucxusbdevice_info, ucxusbdevice/P_UCXUSBDEVICE_INFO, ucxusbdevice/_UCXUSBDEVICE_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxusbdevice.h
req.include-header: Ucxusbdevice.h
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
-	ucxusbdevice.h
api_name:
-	UCXUSBDEVICE_INFO
product:
- Windows
targetos: Windows
req.typenames: UCXUSBDEVICE_INFO, *PUCXUSBDEVICE_INFO
req.product: Windows 10 or later.
---

# _UCXUSBDEVICE_INFO structure
Contains information about the USB device. This structure is passed by UCX in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187823">EVT_UCX_CONTROLLER_USBDEVICE_ADD</a> event callback function.

## Syntax
```
typedef struct _UCXUSBDEVICE_INFO {
  ULONG                Size;
  USB_DEVICE_SPEED     DeviceSpeed;
  UCXUSBDEVICE         TtHub;
  USB_DEVICE_PORT_PATH PortPath;
} UCXUSBDEVICE_INFO, *PUCXUSBDEVICE_INFO;
```

## Members


`Size`

The size in bytes of this structure.

`DeviceSpeed`

Defines the device speed of the USB device or hub.

`TtHub`

A handle to the USB  device object that represents the TT hub.

`PortPath`

The port path for the USB device or hub.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucxusbdevice.h (include Ucxusbdevice.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt187823">EVT_UCX_CONTROLLER_USBDEVICE_ADD</a>