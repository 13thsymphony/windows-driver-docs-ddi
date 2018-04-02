---
UID: NS:usbioctl._USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION
title: "_USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION"
author: windows-driver-content
description: Contains registration information filled when the IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE request completes.
old-location: buses\usb_transport_characteristics_change_notification.htm
old-project: usbref
ms.assetid: C7E1996F-E00C-4A89-8CE4-E9B4987AEED1
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION, PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION, PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION structure pointer [Buses], USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION, USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION structure [Buses], _USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION, buses.usb_transport_characteristics_change_notification, usbioctl/PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION, usbioctl/_USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbioctl.h
req.include-header: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Usbioctl.h
api_name:
-	USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION
product: Windows
targetos: Windows
req.typenames: USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION, *PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION
req.product: Windows 10 or later.
---

# _USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION structure
Contains registration information filled when the <a href="https://msdn.microsoft.com/4192501F-5A30-463C-924D-CD4F2C8C3764">IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a> 

request completes.

## Syntax
```
typedef struct _USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION {
  USB_CHANGE_REGISTRATION_HANDLE Handle;
  USB_TRANSPORT_CHARACTERISTICS  UsbTransportCharacteristics;
} *PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION, USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION;
```

## Members


`Handle`

An opaque handle for this registration.

`UsbTransportCharacteristics`

A <a href="https://msdn.microsoft.com/56394A88-7231-4693-8DD1-C5C7586E490C">USB_TRANSPORT_CHARACTERISTICS</a> structure that is filled by the USB driver stack with the initial values of the transport characteristics.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbioctl.h |

## See Also

<a href="https://msdn.microsoft.com/4192501F-5A30-463C-924D-CD4F2C8C3764">IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a>