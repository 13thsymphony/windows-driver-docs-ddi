---
UID: NC:udecxusbdevice.EVT_UDECX_USB_DEVICE_D0_ENTRY
title: EVT_UDECX_USB_DEVICE_D0_ENTRY
author: windows-driver-content
description: The USB device emulation class extension (UdeCx) invokes this callback function when it gets a request to bring the virtual USB device out of a low power state to working state.
old-location: buses\evt_udecx_usb_device_d0_entry.htm
old-project: usbref
ms.assetid: 92CEEAF3-BD70-4B1C-8385-00720A195E50
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: EVT_UDECX_USB_DEVICE_D0_ENTRY, EvtUsbDeviceLinkPowerEntry, EvtUsbDeviceLinkPowerEntry callback function [Buses], buses.evt_udecx_usb_device_d0_entry, udecxusbdevice/EvtUsbDeviceLinkPowerEntry
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	udecxusbdevice.h
api_name:
-	EvtUsbDeviceLinkPowerEntry
product: Windows
targetos: Windows
req.typenames: USB_DEVICE_PORT_PATH, *PUSB_DEVICE_PORT_PATH
req.product: Windows 10 or later.
---


# EVT_UDECX_USB_DEVICE_D0_ENTRY callback function
The USB device emulation class extension (UdeCx) invokes this callback function when it gets a request to bring the virtual USB device out of a low power state to working state.

## Syntax

```
EVT_UDECX_USB_DEVICE_D0_ENTRY EvtUdecxUsbDeviceD0Entry;

_IRQL_requires_same_ NTSTATUS EvtUdecxUsbDeviceD0Entry(
  WDFDEVICE UdecxWdfDevice,
  UDECXUSBDEVICE UdecxUsbDevice
)
{...}
```

## Parameters

`UdecxWdfDevice`

A handle to a framework device object that represents the controller to which the USB device is attached. The client driver initialized this object in a previous call to <a href="..\udecxwdfdevice\nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation.md">UdecxWdfDeviceAddUsbDeviceEmulation</a>.

`UdecxUsbDevice`

A handle to UDE device object. The client driver created this object in a previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdevicecreate.md">UdecxUsbDeviceCreate</a>.


## Return Value

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE.

## Remarks

The client driver registered the function in a previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitsetstatechangecallbacks.md">UdecxUsbDeviceInitSetStateChangeCallbacks</a> by supplying a function pointer to its implementation.

In the callback implementation, the client driver for the USB device is expected to perform steps to enter working state. 

The power request may be completed asynchronously by returning STATUS_PENDING, and then later completing it by calling <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdevicelinkpowerexitcomplete.md">UdecxUsbDeviceLinkPowerExitComplete</a> with the actual completion code.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Header** | udecxusbdevice.h (include Udecx.h) |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_d0_exit.md">EVT_UDECX_USB_DEVICE_D0_EXIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>



<a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdevicesignalwake.md">UdecxUsbDeviceSignalWake</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdevicelinkpowerexitcomplete.md">UdecxUsbDeviceLinkPowerExitComplete</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UDECX_USB_DEVICE_D0_ENTRY callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>