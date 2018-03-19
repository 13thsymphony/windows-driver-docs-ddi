---
UID: NS:udecxusbdevice._UDECX_USB_DEVICE_PLUG_IN_OPTIONS
title: "_UDECX_USB_DEVICE_PLUG_IN_OPTIONS"
author: windows-driver-content
description: Contains the port numbers to which a virtual USB device is connected. Initialize this structure by calling the UDECX_USB_DEVICE_PLUG_IN_OPTIONS_INIT method.
old-location: buses\udecx_usb_device_plug_in_options.htm
old-project: usbref
ms.assetid: D09A124A-82F6-4B0A-B60F-E60EB54B0EC1
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUDECX_USB_DEVICE_PLUG_IN_OPTIONS, PUDECX_USB_DEVICE_PLUG_IN_OPTIONS, PUDECX_USB_DEVICE_PLUG_IN_OPTIONS structure pointer [Buses], UDECX_USB_DEVICE_PLUG_IN_OPTIONS, UDECX_USB_DEVICE_PLUG_IN_OPTIONS structure [Buses], _UDECX_USB_DEVICE_PLUG_IN_OPTIONS, buses.udecx_usb_device_plug_in_options, udecxusbdevice/ PUDECX_USB_DEVICE_PLUG_IN_OPTIONS, udecxusbdevice/UDECX_USB_DEVICE_PLUG_IN_OPTIONS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: udecxusbdevice.h
req.include-header: Udecx.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	UdecxUsbDevice.h
api_name:
-	UDECX_USB_DEVICE_PLUG_IN_OPTIONS
product: Windows
targetos: Windows
req.typenames: UDECX_USB_DEVICE_PLUG_IN_OPTIONS, *PUDECX_USB_DEVICE_PLUG_IN_OPTIONS
req.product: Windows 10 or later.
---

# _UDECX_USB_DEVICE_PLUG_IN_OPTIONS structure
Contains the port numbers to which a virtual USB device is connected. Initialize this structure by calling the <a href="..\udecxusbdevice\nf-udecxusbdevice-udecx_usb_device_plug_in_options_init.md">UDECX_USB_DEVICE_PLUG_IN_OPTIONS_INIT</a> method.

## Syntax
````
typedef struct _UDECX_USB_DEVICE_PLUG_IN_OPTIONS {
  ULONG Size;
  ULONG Usb20PortNumber;
  ULONG Usb30PortNumber;
} UDECX_USB_DEVICE_PLUG_IN_OPTIONS, * PUDECX_USB_DEVICE_PLUG_IN_OPTIONS;
````

## Members


`Size`

The size of this structure.

`Usb20PortNumber`

The USB 2.0 port number.

`Usb30PortNumber`

The USB 2.0 port number.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | udecxusbdevice.h (include Udecx.h) |

## See Also

<a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceplugin.md">UdecxUsbDevicePlugIn</a>