---
UID: NF:udecxusbdevice.UdecxUsbDevicePlugOutAndDelete
title: UdecxUsbDevicePlugOutAndDelete function
author: windows-driver-content
description: Disconnects the virtual USB device.
old-location: buses\udecxusbdeviceplugoutanddelete.htm
old-project: usbref
ms.assetid: 27816655-1FE9-44A0-81BB-59808FE6F064
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UdecxUsbDevicePlugOutAndDelete, UdecxUsbDevicePlugOutAndDelete function [Buses], buses.udecxusbdeviceplugoutanddelete, udecxusbdevice/UdecxUsbDevicePlugOutAndDelete
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
-	UdecxUsbDevicePlugOutAndDelete
product: Windows
targetos: Windows
req.typenames: UDECX_USB_DEVICE_WAKE_SETTING, *PUDECX_USB_DEVICE_WAKE_SETTING
req.product: Windows 10 or later.
---


# UdecxUsbDevicePlugOutAndDelete function
Disconnects  the virtual USB device.

## Syntax

````
NTSTATUS UdecxUsbDevicePlugOutAndDelete(
  _In_ UDECXUSBDEVICE UdecxUsbDevice
);
````

## Parameters

`UdecxUsbDevice`

A handle to UDE device object. The client driver retrieved this pointer in the previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdevicecreate.md">UdecxUsbDeviceCreate</a>.


## Return Value

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.

## Remarks

If the USB device needs to be removed at runtime, the client driver can call this method to indicate a disconnect event. After this call completes, the client driver can no longer use the device specified by the UdecxUsbDevice parameter; it must create another device by calling <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdevicecreate.md">UdecxUsbDeviceCreate</a>.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>