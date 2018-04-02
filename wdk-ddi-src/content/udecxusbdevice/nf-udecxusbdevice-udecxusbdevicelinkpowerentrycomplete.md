---
UID: NF:udecxusbdevice.UdecxUsbDeviceLinkPowerEntryComplete
title: UdecxUsbDeviceLinkPowerEntryComplete function
author: windows-driver-content
description: Completes an asynchronous request for bringing the device out of a low power state.
old-location: buses\udecxusbdevicelinkpowerentrycomplete.htm
old-project: usbref
ms.assetid: 0B8FF9EB-63E5-4532-B13C-CF0FF04D9A53
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UdecxUsbDeviceLinkPowerEntryComplete, UdecxUsbDeviceLinkPowerEntryComplete function [Buses], buses.udecxusbdevicelinkpowerentrycomplete, udecxusbdevice/UdecxUsbDeviceLinkPowerEntryComplete
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
-	UdecxUsbDeviceLinkPowerEntryComplete
product: Windows
targetos: Windows
req.typenames: UDECX_USB_DEVICE_WAKE_SETTING, *PUDECX_USB_DEVICE_WAKE_SETTING
req.product: Windows 10 or later.
---


# UdecxUsbDeviceLinkPowerEntryComplete function
Completes an asynchronous request for bringing the device out of a low power state.

## Syntax

```
void UdecxUsbDeviceLinkPowerEntryComplete(
  UDECXUSBDEVICE UdecxUsbDevice,
  NTSTATUS       CompletionStatus
);
```

## Parameters

`UdecxUsbDevice`

A handle to UDE device object. The client driver retrieved this pointer in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt595959">UdecxUsbDeviceCreate</a>.

`CompletionStatus`

An appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code that indicates the success or failure of the asynchronous operation.


## Return Value

This function does not return a value.

## Remarks

When the USB device emulation class extension (UdeCx) gets a request to bring the device from low power state and enter working state, it invokes the client driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt595910">EVT_UDECX_USB_DEVICE_D0_ENTRY</a> callback function. 

After the client driver has performed the necessary steps for bringing the virtual USB device to working state, the driver calls this method to notify the class extension that it has completed the power request.

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



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595910">EVT_UDECX_USB_DEVICE_D0_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>