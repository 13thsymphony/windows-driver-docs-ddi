---
UID: NF:udecxusbdevice.UdecxUsbDeviceInitSetStateChangeCallbacks
title: UdecxUsbDeviceInitSetStateChangeCallbacks function
author: windows-driver-content
description: Initializes a WDF-allocated structure with pointers to callback functions.
old-location: buses\udecxusbdeviceinitsetstatechangecallbacks.htm
old-project: usbref
ms.assetid: A4D0B6BC-56FD-4378-A8F9-0A306D3FF22F
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UdecxUsbDeviceInitSetStateChangeCallbacks, buses.udecxusbdeviceinitsetstatechangecallbacks, UdecxUsbDeviceInitSetStateChangeCallbacks function [Buses], udecxusbdevice/UdecxUsbDeviceInitSetStateChangeCallbacks
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Udecxstub.lib
-	Udecxstub.dll
apiname:
-	UdecxUsbDeviceInitSetStateChangeCallbacks
product: Windows
targetos: Windows
req.typenames: "*PUDECX_USB_DEVICE_WAKE_SETTING, UDECX_USB_DEVICE_WAKE_SETTING"
req.product: Windows 10 or later.
---


# UdecxUsbDeviceInitSetStateChangeCallbacks function
Initializes a WDF-allocated structure with pointers to callback functions.

## Syntax

````
void UdecxUsbDeviceInitSetStateChangeCallbacks(
  _Inout_ PUDECXUSBDEVICE_INIT                     UdecxUsbDeviceInit,
  _In_    PUDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS Callbacks
);
````

## Parameters

`UdecxUsbDeviceInit`

A pointer to a WDF-allocated structure that contains initialization parameters for the virtual USB device.  The client driver retrieved this pointer in the previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitallocate.md">UdecxUsbDeviceInitAllocate</a>.

`Callbacks`

A pointer to a <a href="..\udecxusbdevice\ns-udecxusbdevice-_udecx_usb_device_state_change_callbacks.md">UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS</a> structure that contains pointers to callback functions implemented by the client driver.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Header** | udecxusbdevice.h (include Udecx.h) |
| **Library** | Udecxstub.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>

<a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitallocate.md">UdecxUsbDeviceInitAllocate</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UdecxUsbDeviceInitSetStateChangeCallbacks function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>