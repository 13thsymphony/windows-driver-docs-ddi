---
UID: NS:ufxbase._UFX_DEVICE_CAPABILITIES
title: "_UFX_DEVICE_CAPABILITIES"
author: windows-driver-content
description: The UFX_DEVICE_CAPABILITIES structure is used USB to define properties of the Universal Serial Bus (USB) device created by the controller.
old-location: buses\ufx_device_capabilities.htm
old-project: usbref
ms.assetid: 896919C9-E72E-4C0F-9E3E-9BEE9F55D27D
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUFX_DEVICE_CAPABILITIES, PUFX_DEVICE_CAPABILITIES, PUFX_DEVICE_CAPABILITIES structure pointer [Buses], UFX_DEVICE_CAPABILITIES, UFX_DEVICE_CAPABILITIES structure [Buses], _UFX_DEVICE_CAPABILITIES, buses.ufx_device_capabilities, ufxbase/PUFX_DEVICE_CAPABILITIES, ufxbase/UFX_DEVICE_CAPABILITIES"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ufxbase.h
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
-	ufxbase.h
api_name:
-	UFX_DEVICE_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: UFX_DEVICE_CAPABILITIES, *PUFX_DEVICE_CAPABILITIES
req.product: Windows 10 or later.
---

# _UFX_DEVICE_CAPABILITIES structure
The <b>UFX_DEVICE_CAPABILITIES</b> structure is used USB to define properties of the Universal Serial Bus (USB) device created by the controller.

## Syntax
```
typedef struct _UFX_DEVICE_CAPABILITIES {
  ULONG            Size;
  USB_DEVICE_SPEED MaxSpeed;
  ULONG            RemoteWakeSignalDelay;
  BOOLEAN          PdcpSupported;
  USHORT           InEndpointBitmap;
  USHORT           OutEndpointBitmap;
} UFX_DEVICE_CAPABILITIES, *PUFX_DEVICE_CAPABILITIES;
```

## Members


`Size`

Size of the <b>UFX_DEVICE_CAPABILITIES</b> structure.

`MaxSpeed`

Indicates the maximum USB speed supported by the device.

`RemoteWakeSignalDelay`

The minimum time interval in milliseconds to wait after being suspended before requesting remote wakeup.

`PdcpSupported`

If  <b>true</b>, indicates the client driver supports proprietary charger detection.

`InEndpointBitmap`

A bitmap that defines which endpoint numbers can support an IN endpoint.  Bit 0 indicates endpoint address 0, bit 1 indicates endpoint address 1, etc.   Bit 0 (the default control endpoint) is required to be set to 1.

`OutEndpointBitmap`

A bitmap that defines which endpoint numbers can support an OUT endpoint.  Bit 0 indicates endpoint address 0, bit 1 indicates endpoint address 1, etc.   Bit 0 (the default control endpoint) is required to be set to 1.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ufxbase.h |