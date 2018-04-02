---
UID: NE:usbioctl._USB_HUB_TYPE
title: "_USB_HUB_TYPE"
author: windows-driver-content
description: The USB_HUB_TYPE enumeration defines constants that indicate the type of USB hub. The hub type is retrieved by the IOCTL_USB_GET_HUB_INFORMATION_EX I/O control request.
old-location: buses\usb_hub_type.htm
old-project: usbref
ms.assetid: F7516B20-B30F-47BE-BBF3-AB5758D5CF73
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: USB_HUB_TYPE, USB_HUB_TYPE enumeration [Buses], Usb20Hub, Usb30Hub, UsbRootHub, _USB_HUB_TYPE, buses.usb_hub_type, usbioctl/USB_HUB_TYPE, usbioctl/Usb20Hub, usbioctl/Usb30Hub, usbioctl/UsbRootHub
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbioctl.h
api_name:
-	USB_HUB_TYPE
product:
- Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# _USB_HUB_TYPE Enumeration
The <b>USB_HUB_TYPE</b> enumeration defines constants that indicate the type of USB hub.

The hub type is retrieved by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450860">IOCTL_USB_GET_HUB_INFORMATION_EX</a> I/O control request.

The request retrieves the hub descriptor associated with the specified hub in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406262">USB_HUB_INFORMATION_EX</a> structure. The   <b>HubType</b> member contains a <b>USB_HUB_TYPE</b> enumerator that the application can use to evaluate the type of hub descriptor retrieved by the request.

## Syntax
```
typedef enum _USB_HUB_TYPE {
  UsbRootHub  ,
  Usb20Hub    ,
  Usb30Hub
} USB_HUB_TYPE;
```

## Constants

<table>
            
                <tr>
                    <td>UsbRootHub</td>
                    <td>Indicates a root hub.</td>
                </tr>
            
                <tr>
                    <td>Usb20Hub</td>
                    <td>Indicates that the retrieved hub descriptor is defined in USB 2.0 and 1.1 specifications.</td>
                </tr>
            
                <tr>
                    <td>Usb30Hub</td>
                    <td>Indicates that the retrieved hub descriptor is defined in USB 3.0 specification.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | usbioctl.h (include Usbioctl.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450860">IOCTL_USB_GET_HUB_INFORMATION_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539322">USB Constants and Enumerations</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406262">USB_HUB_INFORMATION_EX</a>