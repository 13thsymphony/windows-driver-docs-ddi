---
UID: NS:usbfnbase._USBFN_NOTIFICATION
title: "_USBFN_NOTIFICATION"
author: windows-driver-content
description: Describes information about a Universal Serial Bus (USB) event notification that was received by using IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION.
old-location: buses\usbfn_notification.htm
old-project: usbref
ms.assetid: 84B66823-F357-44DD-A401-79E27FA6B324
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: USBFN_NOTIFICATION structure [Buses], *PUSBFN_NOTIFICATION, _USBFN_NOTIFICATION, PUSBFN_NOTIFICATION structure pointer [Buses], buses.usbfn_notification, PUSBFN_NOTIFICATION, USBFN_NOTIFICATION, usbfnbase/USBFN_NOTIFICATION, usbfnbase/PUSBFN_NOTIFICATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbfnbase.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbfnbase.h
apiname:
-	USBFN_NOTIFICATION
product: Windows
targetos: Windows
req.typenames: "*PUSBFN_NOTIFICATION, USBFN_NOTIFICATION"
req.product: Windows 10 or later.
---

# _USBFN_NOTIFICATION structure
Describes information about a Universal Serial Bus (USB)  event notification that was 
		received by using <a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_bus_event_notification.md">IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION</a>.

## Syntax
````
typedef struct _USBFN_NOTIFICATION {
  USBFN_EVENT Event;
  union {
    USBFN_BUS_SPEED               BusSpeed;
    USB_DEFAULT_PIPE_SETUP_PACKET SetupPacket;
    USHORT                        ConfigurationValue;
    USBFN_PORT_TYPE               PortType;
    ALTERNATE_INTERFACE           AlternateInterface;
  } u;
} USBFN_NOTIFICATION, *PUSBFN_NOTIFICATION;
````

## Members


`Event`

Bus notification indicated by a <a href="..\usbfnbase\ne-usbfnbase-_usbfn_event.md">USBFN_EVENT</a>-typed flag.

`u`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbfnbase.h |