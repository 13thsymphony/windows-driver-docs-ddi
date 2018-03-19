---
UID: NI:ntddser.IOCTL_SERIAL_SET_BAUD_RATE
title: IOCTL_SERIAL_SET_BAUD_RATE
author: windows-driver-content
description: The IOCTL_SERIAL_SET_BAUD_RATE request sets the baud rate on a serial controller device. The serial controller driver verifies the specified baud rate.
old-location: serports\ioctl_serial_set_baud_rate.htm
old-project: serports
ms.assetid: cf3a4b6e-fefa-4a81-84cf-3a4d5529c8a7
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_SERIAL_SET_BAUD_RATE, IOCTL_SERIAL_SET_BAUD_RATE control code [Serial Ports], ntddser/IOCTL_SERIAL_SET_BAUD_RATE, serports.ioctl_serial_set_baud_rate, serref_e71e6ea2-4cac-440d-abc2-40fba2990518.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddser.h
req.include-header: Ntddser.h
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
-	Ntddser.h
api_name:
-	IOCTL_SERIAL_SET_BAUD_RATE
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_SET_BAUD_RATE IOCTL
The <b>IOCTL_SERIAL_SET_BAUD_RATE</b> request sets the baud rate on a serial controller device. The serial controller driver verifies the specified baud rate.

To obtain the baud rate, a client can use an <a href="..\ntddser\ni-ntddser-ioctl_serial_get_baud_rate.md">IOCTL_SERIAL_GET_BAUD_RATE</a> request.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a <a href="..\ntddser\ns-ntddser-_serial_baud_rate.md">SERIAL_BAUD_RATE</a> structure that a client allocates and sets to input the baud rate.

### Input Buffer Length
The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a <a href="..\ntddser\ns-ntddser-_serial_baud_rate.md">SERIAL_BAUD_RATE</a> structure.

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddser.h (include Ntddser.h) |

## See Also

<a href="..\ntddser\ni-ntddser-ioctl_serial_get_baud_rate.md">IOCTL_SERIAL_GET_BAUD_RATE</a>



<a href="..\ntddser\ns-ntddser-_serial_baud_rate.md">SERIAL_BAUD_RATE</a>