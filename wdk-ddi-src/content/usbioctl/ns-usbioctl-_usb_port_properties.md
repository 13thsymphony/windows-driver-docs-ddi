---
UID : NS:usbioctl._USB_PORT_PROPERTIES
title : "_USB_PORT_PROPERTIES"
author : windows-driver-content
description : The USB_PORT_PROPERTIES union is used to report the capabilities of a Universal Serial Bus (USB) port.The port capabilities are retrieved in the USB_PORT_CONNECTOR_PROPERTIES structure by the IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES I/O control request.
old-location : buses\usb_port_properties.htm
old-project : usbref
ms.assetid : BCADC907-3770-4FBE-AEB3-96F93502E899
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : usbioctl/USB_PORT_PROPERTIES, USB_PORT_PROPERTIES, PUSB_PORT_PROPERTIES union pointer [Buses], _USB_PORT_PROPERTIES, PUSB_PORT_PROPERTIES, USB_PORT_PROPERTIES union [Buses], *PUSB_PORT_PROPERTIES, usbioctl/PUSB_PORT_PROPERTIES, buses.usb_port_properties
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : usbioctl.h
req.include-header : Usbioctl.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : None supported
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : "<=DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PUSB_PORT_PROPERTIES, USB_PORT_PROPERTIES"
req.product : Windows 10 or later.
---

# _USB_PORT_PROPERTIES structure
The <b>USB_PORT_PROPERTIES</b> union is used to report the capabilities of a Universal Serial Bus (USB) port.

The  port capabilities are retrieved in the <a href="..\usbioctl\ns-usbioctl-_usb_port_connector_properties.md">USB_PORT_CONNECTOR_PROPERTIES</a> structure by the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_port_connector_properties.md">IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</a> I/O control request.

## Syntax
````
typedef union _USB_PORT_PROPERTIES {
  ULONG  ul;
  struct {
    ULONG PortIsUserConnectable  :1;
    ULONG PortIsDebugCapable  :1;
    ULONG ReservedMBZ  :30;
  };
} USB_PORT_PROPERTIES, *PUSB_PORT_PROPERTIES;
````

## Members


`ul`

A bitmask that indicates the properties and capabilities of the port.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | usbioctl.h (include Usbioctl.h) |

## See Also

<a href="..\usbioctl\ns-usbioctl-_usb_port_connector_properties.md">USB_PORT_CONNECTOR_PROPERTIES</a>

<a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_port_connector_properties.md">IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_PORT_PROPERTIES union%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>