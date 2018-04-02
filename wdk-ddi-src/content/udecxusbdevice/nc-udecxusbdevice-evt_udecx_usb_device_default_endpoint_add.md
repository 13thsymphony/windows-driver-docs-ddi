---
UID: NC:udecxusbdevice.EVT_UDECX_USB_DEVICE_DEFAULT_ENDPOINT_ADD
title: EVT_UDECX_USB_DEVICE_DEFAULT_ENDPOINT_ADD
author: windows-driver-content
description: The USB device emulation class extension (UdeCx) invokes this callback function to request the client driver to create the default control endpoint on the virtual USB device.
old-location: buses\evt_udecx_usb_device_default_endpoint_add.htm
old-project: usbref
ms.assetid: 575FA7CD-3F29-40A6-9625-EB8183AA05BA
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: EVT_UDECX_USB_DEVICE_DEFAULT_ENDPOINT_ADD, EvtUsbDeviceDefaultEndpointAdd, EvtUsbDeviceDefaultEndpointAdd callback function [Buses], buses.evt_udecx_usb_device_default_endpoint_add, udecxusbdevice/EvtUsbDeviceDefaultEndpointAdd
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	UdecxUsbDevice.h
api_name:
-	EvtUsbDeviceDefaultEndpointAdd
product: Windows
targetos: Windows
req.typenames: USB_DEVICE_PORT_PATH, *PUSB_DEVICE_PORT_PATH
req.product: Windows 10 or later.
---


# EVT_UDECX_USB_DEVICE_DEFAULT_ENDPOINT_ADD callback function
The USB device emulation class extension (UdeCx) invokes this callback function to request the client driver to create the default control endpoint on the virtual USB device.

## Syntax

```
EVT_UDECX_USB_DEVICE_DEFAULT_ENDPOINT_ADD EvtUdecxUsbDeviceDefaultEndpointAdd;

_IRQL_requires_same_ NTSTATUS EvtUdecxUsbDeviceDefaultEndpointAdd(
  UDECXUSBDEVICE UdecxUsbDevice,
  PUDECXUSBENDPOINT_INIT UdecxEndpointInit
)
{...}
```

## Parameters

`UdecxUsbDevice`

A handle to the UDE device object for which the client driver creates the default endpoint. The driver created this object in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt595959">UdecxUsbDeviceCreate</a>.

`UdecxEndpointInit`

A pointer to an <b>UDECXUSBENDPOINT_INIT</b> structure that the client driver retrieved in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt627989">UdecxUsbSimpleEndpointInitAllocate</a>.


## Return Value

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Header** | udecxusbdevice.h (include Udecx.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt627989">UdecxUsbSimpleEndpointInitAllocate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>