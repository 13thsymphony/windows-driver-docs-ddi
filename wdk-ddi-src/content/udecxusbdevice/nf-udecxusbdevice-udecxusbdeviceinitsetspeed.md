---
UID: NF:udecxusbdevice.UdecxUsbDeviceInitSetSpeed
title: UdecxUsbDeviceInitSetSpeed function
author: windows-driver-content
description: Sets the USB speed of the virtual USB device to create.
old-location: buses\udecxusbdeviceinitsetspeed.htm
old-project: usbref
ms.assetid: D7EF9B82-5156-4F27-AA52-94C113C81D3A
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UdecxUsbDeviceInitSetSpeed, UdecxUsbDeviceInitSetSpeed function [Buses], buses.udecxusbdeviceinitsetspeed, udecxusbdevice/UdecxUsbDeviceInitSetSpeed
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: udecxusbdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Udecxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Udecxstub.lib
-	Udecxstub.dll
api_name:
-	UdecxUsbDeviceInitSetSpeed
product:
- Windows
targetos: Windows
req.typenames: UDECX_USB_DEVICE_WAKE_SETTING, *PUDECX_USB_DEVICE_WAKE_SETTING
req.product: Windows 10 or later.
---


# UdecxUsbDeviceInitSetSpeed function
Sets the USB speed of the virtual USB device to create.

## Syntax

```
void UdecxUsbDeviceInitSetSpeed(
  PUDECXUSBDEVICE_INIT   UdecxUsbDeviceInit,
  UDECX_USB_DEVICE_SPEED UsbDeviceSpeed
);
```

## Parameters

`UdecxUsbDeviceInit`

A pointer to a WDF-allocated structure that contains initialization parameters for the virtual USB device.  The client driver retrieved this pointer in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt627968">UdecxUsbDeviceInitAllocate</a>.

`UsbDeviceSpeed`

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt628002">UDECX_USB_DEVICE_SPEED</a>-type value that indicates the USB speed to set.


## Return Value

This function does not return a value.

## Remarks

After the client driver sets the USB speed of the device, it only operates in that speed. The speed also determines the kind of port to which the device can connect. For example, a USB SuperSpeed device cannot connect to a USB 2.0 port.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Header** | udecxusbdevice.h (include Udecx.h) |
| **Library** | Udecxstub.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>