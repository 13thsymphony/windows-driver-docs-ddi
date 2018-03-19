---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION
title: IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION
author: windows-driver-content
description: The USB class driver sends this request to prepare for notifications received from the USB function class extension (UFX) in response to an event on the bus, such as a change in the port type or a receipt of a non-standard setup packet.
old-location: buses\ioctl_internal_usbfn_bus_event_notification.htm
old-project: usbref
ms.assetid: 737EDB43-FAFF-4EFD-A7A1-206D646F23E1
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION, IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION control code [Buses], buses.ioctl_internal_usbfn_bus_event_notification, usbfnioctl/IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbfnioctl.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbfnioctl.h
api_name:
-	IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION
product: Windows
targetos: Windows
req.typenames: USBFN_USB_STRING, *PUSBFN_USB_STRING
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION IOCTL
The USB class driver sends this request to prepare for notifications received from the USB function class extension (UFX) in response to an event on the bus, such as a change in the port type 
		or a receipt of a non-standard setup packet.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
NULL.

### Input Buffer Length
None.

### Output Buffer
A pointer to a caller-allocated <a href="..\usbfnbase\ns-usbfnbase-_usbfn_notification.md">USBFN_NOTIFICATION</a> 
			structure that UFX populates with the type of bus event and data associated with that event.

### Output Buffer Length
The size of a <a href="..\usbfnbase\ns-usbfnbase-_usbfn_notification.md">USBFN_NOTIFICATION</a> 
			structure.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE.

## Remarks
UFX completes this request in response to an event on the bus. It is recommended that class drivers send multiple requests at a time to make sure that critical notifications are not missed.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbfnioctl.h |

## See Also

<a href="..\usbfnbase\ns-usbfnbase-_usbfn_notification.md">USBFN_NOTIFICATION</a>



<a href="..\usbfnbase\ne-usbfnbase-_usbfn_event.md">USBFN_EVENT</a>