---
UID: NS.USBFNBASE._USBFN_NOTIFICATION
title: _USBFN_NOTIFICATION
author: windows-driver-content
description: Describes information about a Universal Serial Bus (USB) event notification that was received by using IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION.
old-location: buses\usbfn_notification.htm
old-project: usbref
ms.assetid: 84B66823-F357-44DD-A401-79E27FA6B324
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _USBFN_NOTIFICATION, *PUSBFN_NOTIFICATION, USBFN_NOTIFICATION
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
req.alt-api: USBFN_NOTIFICATION
req.alt-loc: usbfnbase.h
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
req.product: Windows 10 or later.
---

# _USBFN_NOTIFICATION structure



## -description
Describes information about a Universal Serial Bus (USB)  event notification that was 
		received by using <a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_bus_event_notification.md">IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION</a>.
		



## -syntax

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


## -struct-fields

### -field Event

Bus notification indicated by a <a href="buses.usbfn_event">USBFN_EVENT</a>-typed flag.


### -field u


### -field BusSpeed

The operating bus speed indicated by <a href="buses.usbfn_bus_speed">USBFN_BUS_SPEED</a>-typed flags.


### -field SetupPacket

Describes a setup packet in a  <b>USB_DEFAULT_PIPE_SETUP_PACKET</b> structure for a control transfer to or from the default endpoint as indicated by a <b>USB_DEFAULT_PIPE_SETUP_PACKET</b>-typed flag.


### -field ConfigurationValue

The <b>bConfigurationValue</b> field of a USB configuration descriptor.


### -field PortType

Possible port types supported by a function controller indicated by a <a href="buses.usbfn_port_type">USBFN_PORT_TYPE</a>-typed flag.


### -field AlternateInterface

Alternate setting of the interface indicated by <a href="buses.alternate_interface">ALTERNATE_INTERFACE</a>.

</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Usbfnbase.h</dt>
</dl>
</td>
</tr>
</table>