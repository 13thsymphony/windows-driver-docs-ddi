---
UID: NS:udecxwdfdevice._UDECX_WDF_DEVICE_CONFIG
title: "_UDECX_WDF_DEVICE_CONFIG"
author: windows-driver-content
description: Contains pointers to event callback functions implemented by the UDE client driver for a USB host controller. Initialize this structure by calling UDECX_WDF_DEVICE_CONFIG_INIT.
old-location: buses\udecx_wdf_device_config.htm
old-project: usbref
ms.assetid: 54853C39-FA6C-4F9B-A202-F116C43D3A4E
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUDECX_WDF_DEVICE_CONFIG, PUDECX_WDF_DEVICE_CONFIG, PUDECX_WDF_DEVICE_CONFIG structure pointer [Buses], UDECX_WDF_DEVICE_CONFIG, UDECX_WDF_DEVICE_CONFIG structure [Buses], _UDECX_WDF_DEVICE_CONFIG, buses.udecx_wdf_device_config, udecxwdfdevice/PUDECX_WDF_DEVICE_CONFIG, udecxwdfdevice/UDECX_WDF_DEVICE_CONFIG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: udecxwdfdevice.h
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
-	udecxwdfdevice.h
api_name:
-	UDECX_WDF_DEVICE_CONFIG
product: Windows
targetos: Windows
req.typenames: UDECX_WDF_DEVICE_CONFIG, *PUDECX_WDF_DEVICE_CONFIG
req.product: Windows 10 or later.
---

# _UDECX_WDF_DEVICE_CONFIG structure
Contains pointers to event callback functions implemented by the UDE client driver for a USB host controller. Initialize this structure by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt628010">UDECX_WDF_DEVICE_CONFIG_INIT</a>.

## Syntax
```
typedef struct _UDECX_WDF_DEVICE_CONFIG {
  ULONG                                     Size;
  USHORT                                    NumberOfUsb20Ports;
  USHORT                                    NumberOfUsb30Ports;
  PFN_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY EvtUdecxWdfDeviceQueryUsbCapability;
  UDECX_WDF_DEVICE_RESET_ACTION             ResetAction;
  PFN_UDECX_WDF_DEVICE_RESET                EvtUdecxWdfDeviceReset;
} UDECX_WDF_DEVICE_CONFIG, *PUDECX_WDF_DEVICE_CONFIG;
```

## Members


`Size`

The size of this structure.

`NumberOfUsb20Ports`

The number of USB 2.0 ports on the root hub of the emulated host controller.

`NumberOfUsb30Ports`

The number of USB 3.0 ports on the root hub of the emulated host controller.

`EvtUdecxWdfDeviceQueryUsbCapability`

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt595919">EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY</a> callback function.

`ResetAction`

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt628011">UDECX_WDF_DEVICE_RESET_ACTION</a>-type value that indicates the reset action: each attached device or the host controller.

`EvtUdecxWdfDeviceReset`

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt595920">EVT_UDECX_WDF_DEVICE_RESET</a> callback function.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | udecxwdfdevice.h (include Udecx.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt628010">UDECX_WDF_DEVICE_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt627990">UdecxWdfDeviceAddUsbDeviceEmulation</a>