---
UID : NI:usbscan.IOCTL_WAIT_ON_DEVICE_EVENT
title : IOCTL_WAIT_ON_DEVICE_EVENT
author : windows-driver-content
description : Returns information about an event occurring on a USB interrupt pipe.
old-location : image\ioctl_wait_on_device_event.htm
old-project : image
ms.assetid : 0895a19b-bb28-405a-98df-28522a18ec2b
ms.author : windowsdriverdev
ms.date : 1/17/2018
ms.keywords : _RAW_PIPE_TYPE, RAW_PIPE_TYPE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : usbscan.h
req.include-header : Usbscan.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IOCTL_WAIT_ON_DEVICE_EVENT
req.alt-loc : Usbscan.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : RAW_PIPE_TYPE
req.product : Windows 10 or later.
---

# IOCTL_WAIT_ON_DEVICE_EVENT IOCTL
Returns information about an event occurring on a USB interrupt pipe.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<b>NULL</b>

### Input Buffer Length
Zero.

### Output Buffer
Pointer to a buffer that is large enough to receive the largest packet the device is capable of sending on the interrupt pipe.

### Output Buffer Length
Size of the output buffer.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.

    ## Remarks
        Device handle, obtained by calling <a href="https://msdn.microsoft.com/80a96083-4de9-4422-9705-b8ad2b6cbd1b">CreateFile</a>.

IOCTL_WAIT_ON_DEVICE_EVENT

<b>NULL</b>

Zero.

Pointer to a buffer that is large enough to receive the largest packet the device is capable of sending on the interrupt pipe.

Size of the output buffer.

Pointer to a location to receive the number of bytes returned.

Optional pointer to an OVERLAPPED structure (described in the Microsoft Windows SDK documentation).

When the <b>DeviceloControl</b> function is called with the IOCTL_WAIT_ON_DEVICE_EVENT control code, the caller must specify a buffer pointer as the function's <i>lpOutBuffer</i> parameter. The buffer must be large enough to hold the largest packet the device can send on its interrupt pipe.

The type and size of information returned are device-specific. For example, a still image device might issue an interrupt when a user presses one of its buttons, and the return packet might indicate which button was pressed.

For more information, see <a href="https://msdn.microsoft.com/f9216d3c-4930-4c26-8eac-6ee500b038e0">Accessing Kernel-Mode Drivers for Still Image Devices</a>.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | usbscan.h (include Usbscan.h) |
| **IRQL** |  |