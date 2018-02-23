---
UID: NS:usbioctl._USB_NODE_CONNECTION_DRIVERKEY_NAME
title: "_USB_NODE_CONNECTION_DRIVERKEY_NAME"
author: windows-driver-content
description: The USB_NODE_CONNECTION_DRIVERKEY_NAME structure is used with the IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME I/O control request to retrieve the driver key name for the device that is connected to the indicated port.
old-location: buses\usb_node_connection_driverkey_name.htm
old-project: UsbRef
ms.assetid: b5939a5b-2856-494c-9673-d32e2fc93384
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: usbstrct_561b9eb1-d580-48c5-ac16-c87647f7a342.xml, PUSB_NODE_CONNECTION_DRIVERKEY_NAME structure pointer [Buses], _USB_NODE_CONNECTION_DRIVERKEY_NAME, usbioctl/PUSB_NODE_CONNECTION_DRIVERKEY_NAME, USB_NODE_CONNECTION_DRIVERKEY_NAME, USB_NODE_CONNECTION_DRIVERKEY_NAME structure [Buses], PUSB_NODE_CONNECTION_DRIVERKEY_NAME, buses.usb_node_connection_driverkey_name, *PUSB_NODE_CONNECTION_DRIVERKEY_NAME, usbioctl/USB_NODE_CONNECTION_DRIVERKEY_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbioctl.h
req.include-header: Usbioctl.h
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbioctl.h
apiname:
-	USB_NODE_CONNECTION_DRIVERKEY_NAME
product: Windows
targetos: Windows
req.typenames: USB_NODE_CONNECTION_DRIVERKEY_NAME, *PUSB_NODE_CONNECTION_DRIVERKEY_NAME
req.product: Windows 10 or later.
---

# _USB_NODE_CONNECTION_DRIVERKEY_NAME structure
The <b>USB_NODE_CONNECTION_DRIVERKEY_NAME</b> structure is used with the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_node_connection_driverkey_name.md">IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME</a> I/O control request to retrieve the driver key name for the device that is connected to the indicated port.

## Syntax
````
typedef struct _USB_NODE_CONNECTION_DRIVERKEY_NAME {
  ULONG ConnectionIndex;
  ULONG ActualLength;
  WCHAR DriverKeyName[1];
} USB_NODE_CONNECTION_DRIVERKEY_NAME, *PUSB_NODE_CONNECTION_DRIVERKEY_NAME;
````

## Members


`ActualLength`

On output, the length, in bytes, of the string in <b>DriverKeyName</b>.

`ConnectionIndex`

On input, the port number that the device is connected to.

`DriverKeyName`

On output, the driver key name for the device that is attached to the port that is indicated by <b>ConnectionIndex</b>. This name is represented as a Unicode string.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbioctl.h (include Usbioctl.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_node_connection_driverkey_name.md">IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20USB_NODE_CONNECTION_DRIVERKEY_NAME structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>