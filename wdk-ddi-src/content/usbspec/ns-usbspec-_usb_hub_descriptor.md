---
UID: NS:usbspec._USB_HUB_DESCRIPTOR
title: "_USB_HUB_DESCRIPTOR"
author: windows-driver-content
description: The USB_HUB_DESCRIPTOR structure contains a hub descriptor.
old-location: buses\usb_hub_descriptor.htm
old-project: usbref
ms.assetid: 6f5521f4-44da-4470-b649-d98c1d4e4891
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSB_HUB_DESCRIPTOR, PUSB_HUB_DESCRIPTOR, PUSB_HUB_DESCRIPTOR structure pointer [Buses], USB_HUB_DESCRIPTOR, USB_HUB_DESCRIPTOR structure [Buses], _USB_HUB_DESCRIPTOR, buses.usb_hub_descriptor, usbspec/PUSB_HUB_DESCRIPTOR, usbspec/USB_HUB_DESCRIPTOR, usbstrct_b21769d6-aab1-43b9-8d48-bde249f5c325.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbspec.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbspec.h
api_name:
-	USB_HUB_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: USB_HUB_DESCRIPTOR, *PUSB_HUB_DESCRIPTOR
req.product: Windows 10 or later.
---

# _USB_HUB_DESCRIPTOR structure
The <b>USB_HUB_DESCRIPTOR</b> structure contains a hub descriptor.

## Syntax
````
typedef struct _USB_HUB_DESCRIPTOR {
  UCHAR  bDescriptorLength;
  UCHAR  bDescriptorType;
  UCHAR  bNumberOfPorts;
  USHORT wHubCharacteristics;
  UCHAR  bPowerOnToPowerGood;
  UCHAR  bHubControlCurrent;
  UCHAR  bRemoveAndPowerMask[64];
} USB_HUB_DESCRIPTOR, *PUSB_HUB_DESCRIPTOR;
````

## Members


`bDescriptorLength`

The length, in bytes, of the descriptor.

`bDescriptorType`

The descriptor type. For hub descriptors, this value should be 0x29.

`bHubControlCurrent`

The maximum current requirements, in milliamperes, of the controller component of the hub.

`bNumberOfPorts`

The number of ports on the hub.

`bPowerOnToPowerGood`

The time, in 2-millisecond intervals, that it takes the device to turn on completely. For more information about this member, see Universal Serial Bus Specification.

`bRemoveAndPowerMask`

Not currently implemented. Do not use this member. 

This member implements DeviceRemovable and PortPwrCtrlMask fields of the hub descriptor. For more information about these fields, see Universal Serial Bus Specification.

`wHubCharacteristics`

The hub characteristics. For more information about this member, see Universal Serial Bus Specification.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbspec.h (include Usbioctl.h) |

## See Also

<a href="..\usbioctl\ns-usbioctl-_usb_hub_information.md">USB_HUB_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_HUB_DESCRIPTOR structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>