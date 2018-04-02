---
UID: NI:ntddser.IOCTL_SERIAL_GET_HANDFLOW
title: IOCTL_SERIAL_GET_HANDFLOW
author: windows-driver-content
description: The IOCTL_SERIAL_GET_HANDFLOW request returns information about the configuration of the handshake flow control set for a serial device.
old-location: serports\ioctl_serial_get_handflow.htm
old-project: serports
ms.assetid: d1d918fb-1ccb-46e6-ad28-e48daf226b3a
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_SERIAL_GET_HANDFLOW, IOCTL_SERIAL_GET_HANDFLOW control code [Serial Ports], ntddser/IOCTL_SERIAL_GET_HANDFLOW, serports.ioctl_serial_get_handflow, serref_caa7cdf7-cf60-4baa-88bf-43a7db423a37.xml
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
-	IOCTL_SERIAL_GET_HANDFLOW
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_GET_HANDFLOW IOCTL
The <b>IOCTL_SERIAL_GET_HANDFLOW</b> request returns information about the configuration of the handshake flow control set for a serial device.

To set the configuration of the handshake flow control, a client can use an <a href="https://msdn.microsoft.com/library/windows/hardware/ff546736">IOCTL_SERIAL_SET_HANDFLOW</a> request.

For more information about the settings for handshake flow control, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj680685">SERIAL_HANDFLOW</a>.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated <b>SERIAL_HANDFLOW</b> structure that the serial controller driver uses to output information about the configuration of handshake flow control.

### Output Buffer Length
The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a <b>SERIAL_HANDFLOW</b> structure.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a <b>SERIAL_HANDFLOW</b> structure. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddser.h (include Ntddser.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546736">IOCTL_SERIAL_SET_HANDFLOW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj680685">SERIAL_HANDFLOW</a>