---
UID: NS:usbioctl._USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS
title: "_USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS"
author: windows-driver-content
description: The USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS union is used to indicate the speed at which a USB 3.0 device is currently operating and whether it can operate at higher speed, when attached to a particular port.
old-location: buses\usb_node_connection_information_ex_v2_flags.htm
old-project: usbref
ms.assetid: F066CE0E-3247-4C42-9EF6-8A6EB0C0BC71
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUSB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS, PUSB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS, PUSB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS union pointer [Buses], USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS, USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS union [Buses], _USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS, buses.usb_node_connection_information_ex_v2_flags, usbioctl/PUSB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS, usbioctl/USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Usbioctl.h
api_name:
-	USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS
product: Windows
targetos: Windows
req.typenames: USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS, *PUSB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS
req.product: Windows 10 or later.
---

# _USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS structure
The <b>USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS</b> union is used to indicate the speed at which a USB 3.0  device is currently operating and whether it can operate at higher speed, when attached to a particular port. 

Device speed information is obtained in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406295">USB_NODE_CONNECTION_INFORMATION_EX_V2</a> structure by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450861">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2</a> I/O control request.

Or: the speed in which a device attached to a port is currently operating and at what speeds it is capable of operating.

## Syntax
```
typedef struct _USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS {
  ULONG  ul;
  struct {
    ULONG  : 1  DeviceIsOperatingAtSuperSpeedOrHigher;
    ULONG  : 1  DeviceIsOperatingAtSuperSpeedPlusOrHigher;
    ULONG  : 1  DeviceIsSuperSpeedCapableOrHigher;
    ULONG  : 1  DeviceIsSuperSpeedPlusCapableOrHigher;
    ULONG  : 28 ReservedMBZ;
  };
} *PUSB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS, USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS;
```

## Members


`ul`

A bitmask that indicates the USB speed of the device that is attached to the port.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | usbioctl.h (include Usbioctl.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450861">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406264">USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS</a>