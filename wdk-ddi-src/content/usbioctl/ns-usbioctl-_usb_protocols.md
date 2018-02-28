---
UID: NS:usbioctl._USB_PROTOCOLS
title: "_USB_PROTOCOLS"
author: windows-driver-content
description: The USB_PROTOCOLS union is used to report the Universal Serial Bus (USB) signaling protocols that are supported by the port.
old-location: buses\usb_protocols.htm
old-project: usbref
ms.assetid: F970A7FB-DF6F-414B-8B4B-C7E4C5C620B1
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSB_PROTOCOLS, PUSB_PROTOCOLS, PUSB_PROTOCOLS union pointer [Buses], USB_PROTOCOLS, USB_PROTOCOLS union [Buses], _USB_PROTOCOLS, buses.usb_protocols, usbioctl/PUSB_PROTOCOLS, usbioctl/USB_PROTOCOLS"
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
-	usbioctl.h
api_name:
-	USB_PROTOCOLS
product: Windows
targetos: Windows
req.typenames: USB_PROTOCOLS, *PUSB_PROTOCOLS
req.product: Windows 10 or later.
---

# _USB_PROTOCOLS structure
The <b>USB_PROTOCOLS</b> union is used to report the Universal Serial Bus (USB) signaling protocols that are supported by the port.

The  supported protocols are retrieved in the <a href="..\usbioctl\ns-usbioctl-_usb_node_connection_information_ex_v2.md">USB_NODE_CONNECTION_INFORMATION_EX_V2</a> structure by the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_node_connection_information_ex_v2.md">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2</a> I/O control request.

In the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_node_connection_information_ex_v2.md">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2</a> request, the caller specifies a bitwise <b>OR</b> of one or more flags defined in <b>USB_PROTOCOLS</b>. Upon successful completion, the request retrieves flags, which indicate the protocols that are actually supported by the port.

## Syntax
````
typedef union _USB_PROTOCOLS {
  ULONG  ul;
  struct {
    ULONG Usb110  :1;
    ULONG Usb200  :1;
    ULONG Usb300  :1;
    ULONG ReservedMBZ  :29;
  };
} USB_PROTOCOLS, *PUSB_PROTOCOLS;
````

## Members


`ul`

A bitmask that indicates the USB signaling protocols that are supported by the port.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | usbioctl.h (include Usbioctl.h) |

## See Also

<a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_node_connection_information_ex_v2.md">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2</a>



<a href="..\usbioctl\ns-usbioctl-_usb_node_connection_information_ex_v2.md">USB_NODE_CONNECTION_INFORMATION_EX_V2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_PROTOCOLS union%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>