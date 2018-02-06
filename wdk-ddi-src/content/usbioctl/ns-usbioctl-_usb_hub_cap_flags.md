---
UID: NS:usbioctl._USB_HUB_CAP_FLAGS
title: "_USB_HUB_CAP_FLAGS"
author: windows-driver-content
description: The USB_HUB_CAP_FLAGS structure is used to report the capabilities of a hub.
old-location: buses\usb_hub_cap_flags.htm
old-project: usbref
ms.assetid: 4f3f01f2-d5ef-4b41-8733-ac44952dc9a9
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: USB_HUB_CAP_FLAGS union [Buses], buses.usb_hub_cap_flags, *PUSB_HUB_CAP_FLAGS, usbioctl/PUSB_HUB_CAP_FLAGS, PUSB_HUB_CAP_FLAGS, usbioctl/USB_HUB_CAP_FLAGS, _USB_HUB_CAP_FLAGS, usbstrct_0c0ca119-db83-4486-9b65-f16c70716c14.xml, USB_HUB_CAP_FLAGS, PUSB_HUB_CAP_FLAGS union pointer [Buses]
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
-	USB_HUB_CAP_FLAGS
product: Windows
targetos: Windows
req.typenames: USB_HUB_CAP_FLAGS, *PUSB_HUB_CAP_FLAGS
req.product: Windows 10 or later.
---

# _USB_HUB_CAP_FLAGS structure
The <b>USB_HUB_CAP_FLAGS</b> structure is used to report the capabilities of a hub.

## Syntax
````
typedef union _USB_HUB_CAP_FLAGS {
  ULONG  ul;
  struct {
    ULONG HubIsHighSpeedCapable  :1;
    ULONG HubIsHighSpeed  :1;
    ULONG HubIsMultiTtCapable  :1;
    ULONG HubIsMultiTt  :1;
    ULONG HubIsRoot  :1;
    ULONG HubIsArmedWakeOnConnect  :1;
    ULONG HubIsBusPowered  :1;
    ULONG ReservedMBZ  :25;
  };
} USB_HUB_CAP_FLAGS, *PUSB_HUB_CAP_FLAGS;
````

## Members


`ul`

A bitmask that represents the hub capabilities.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbioctl.h (include Usbioctl.h) |

## See Also

<a href="..\usbioctl\ns-usbioctl-_usb_hub_capabilities_ex.md">USB_HUB_CAPABILITIES_EX</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_HUB_CAP_FLAGS union%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>