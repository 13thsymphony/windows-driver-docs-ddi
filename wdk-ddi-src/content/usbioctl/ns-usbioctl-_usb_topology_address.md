---
UID: NS:usbioctl._USB_TOPOLOGY_ADDRESS
title: "_USB_TOPOLOGY_ADDRESS"
author: windows-driver-content
description: The USB_TOPOLOGY_ADDRESS structure is used with the IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS I/O request to retrieve information about a USB device?s location in the USB device tree.
old-location: buses\usb_topology_address.htm
old-project: usbref
ms.assetid: 5d8d6665-bfa1-4bc5-8168-7508624845e1
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSB_TOPOLOGY_ADDRESS, PUSB_TOPOLOGY_ADDRESS, PUSB_TOPOLOGY_ADDRESS structure pointer [Buses], USB_TOPOLOGY_ADDRESS, USB_TOPOLOGY_ADDRESS structure [Buses], _USB_TOPOLOGY_ADDRESS, buses.usb_topology_address, usbioctl/PUSB_TOPOLOGY_ADDRESS, usbioctl/USB_TOPOLOGY_ADDRESS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later operating systems.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbioctl.h
api_name:
-	USB_TOPOLOGY_ADDRESS
product: Windows
targetos: Windows
req.typenames: USB_TOPOLOGY_ADDRESS, *PUSB_TOPOLOGY_ADDRESS
req.product: Windows 10 or later.
---

# _USB_TOPOLOGY_ADDRESS structure
The <b>USB_TOPOLOGY_ADDRESS</b> structure is used with the <a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_get_topology_address.md">IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS</a> I/O request to retrieve information about a USB device?s location in the USB device tree.

## Syntax
````
typedef struct _USB_TOPOLOGY_ADDRESS {
  ULONG  PciBusNumber;
  ULONG  PciDeviceNumber;
  ULONG  PciFunctionNumber;
  USHORT RootHubPortNumber;
  USHORT HubPortNumber[5];
} USB_TOPOLOGY_ADDRESS, *PUSB_TOPOLOGY_ADDRESS;
````

## Members


`HubPortNumber`

An array containing the port number on each external hub (between the root hub and the device) through which the USB device is connected.  The first element of the array indicates the port on the hub that is connected directly to the root hub.  An array containing all zeros indicates that the device is connected directly to the root hub.

`PciBusNumber`

Specifies the PCI bus number of the USB host controller to which the USB device is attached.

`PciDeviceNumber`

Specifies the PCI device number of the USB host controller to which the USB device is attached.

`PciFunctionNumber`

Specifies the PCI function number of the USB host controller to which the USB device is attached.

`Reserved`



`Reserved2`



`RootHubPortNumber`

Specifies the root hub port number through which the USB device is connected.  The USB device can be connected to the root port directly, or it can be connected through 1 or more external USB hubs to the port.

## Remarks
The reserved members of this structure must be treated as opaque and are reserved for system use.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later operating systems. Available in Windows Vista and later operating systems. |
| **Header** | usbioctl.h (include Usbioctl.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_get_topology_address.md">IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_TOPOLOGY_ADDRESS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>