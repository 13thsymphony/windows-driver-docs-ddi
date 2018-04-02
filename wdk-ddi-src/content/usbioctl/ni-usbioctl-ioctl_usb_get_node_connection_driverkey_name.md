---
UID: NI:usbioctl.IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME
title: IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME
author: windows-driver-content
description: The IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME I/O control request retrieves the driver registry key name that is associated with the device that is connected to the indicated port.
old-location: buses\ioctl_usb_get_node_connection_driverkey_name.htm
old-project: usbref
ms.assetid: e9826b4d-e8ac-495e-8125-7835b62011dc
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME, IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME control code [Buses], buses.ioctl_usb_get_node_connection_driverkey_name, usbioctl/IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME, usbirp_cdc9e1be-96fd-41d4-a0d3-1303b0b4fb1d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
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
-	Usbioctl.h
api_name:
-	IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME
product:
- Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME IOCTL
The <b>IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME</b> I/O control request retrieves the driver registry key name that is associated with the device that is connected to the indicated port. 

<b>IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME</b> is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a user-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff540085">USB_NODE_CONNECTION_DRIVERKEY_NAME</a> structure. On input, the <b>ConnectionIndex</b> member of this structure contains the number of the port that the device is connected to.

### Input Buffer Length
The size of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540085">USB_NODE_CONNECTION_DRIVERKEY_NAME</a> structure.

### Output Buffer
On output, the <b>DriverKeyName</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540085">USB_NODE_CONNECTION_DRIVERKEY_NAME</a> structure at<b> AssociatedIrp.SystemBuffer</b> contains the driver key name that is associated with the device that is connected to the port that is indicated by <b>ConnectionIndex</b>. 

The <b>ActualLength</b> member indicates the length, in bytes, of the driver key name. The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member indicates the size, in bytes, of the entire <a href="https://msdn.microsoft.com/library/windows/hardware/ff540085">USB_NODE_CONNECTION_DRIVERKEY_NAME</a> structure.

### Output Buffer Length
The size of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540085">USB_NODE_CONNECTION_DRIVERKEY_NAME</a> structure.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The USB stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES.

If the caller allocates an output buffer that is large enough to hold all of the output data, <b>IoStatus.Information</b> will be equal to the value of <b>ActualLength</b>. If the output buffer is large enough to hold all of the output data, <b>IoStatus.Information</b> will be equal to <code>sizeof(USB_NODE_CONNECTION_DRIVERKEY_NAME)</code>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbioctl.h (include Usbioctl.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540085">USB_NODE_CONNECTION_DRIVERKEY_NAME</a>