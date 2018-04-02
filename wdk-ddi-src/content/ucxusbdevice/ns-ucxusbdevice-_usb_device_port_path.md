---
UID: NS:ucxusbdevice._USB_DEVICE_PORT_PATH
title: "_USB_DEVICE_PORT_PATH"
author: windows-driver-content
description: Contains the port path of a USB device.
old-location: buses\_usb_device_port_path.htm
old-project: usbref
ms.assetid: 75C7DB08-F831-43ED-8373-F3F4C7AF89E8
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUSB_DEVICE_PORT_PATH, P_USB_DEVICE_PORT_PATH, P_USB_DEVICE_PORT_PATH structure pointer [Buses], USB_DEVICE_PORT_PATH, USB_DEVICE_PORT_PATH structure [Buses], _USB_DEVICE_PORT_PATH, buses._usb_device_port_path, ucxusbdevice/P_USB_DEVICE_PORT_PATH, ucxusbdevice/_USB_DEVICE_PORT_PATH"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
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
-	USB_DEVICE_PORT_PATH
product: Windows
targetos: Windows
req.typenames: USB_DEVICE_PORT_PATH, *PUSB_DEVICE_PORT_PATH
req.product: Windows 10 or later.
---

# _USB_DEVICE_PORT_PATH structure
Contains the port path of a USB device.

## Syntax
```
typedef struct _USB_DEVICE_PORT_PATH {
  ULONG Size;
  ULONG PortPathDepth;
  ULONG TTHubDepth;
  ULONG PortPath[MAX_USB_DEVICE_DEPTH];
} USB_DEVICE_PORT_PATH, *PUSB_DEVICE_PORT_PATH;
```

## Members


`Size`

The size in bytes of this structure.

`PortPathDepth`

The depth of path in the USB topology tree, consisting of host controller, hubs, and devices.

`TTHubDepth`

The depth of path in the USB topology tree from a TT hub.

`PortPath`

The index of connected USB port on the hub.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucxusbdevice.h (include Ucxclass.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt188055">UCXUSBDEVICE_INFO</a>