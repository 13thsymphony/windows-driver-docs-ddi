---
UID : NI:ntddser.IOCTL_SERIAL_SET_TIMEOUTS
title : IOCTL_SERIAL_SET_TIMEOUTS
author : windows-driver-content
description : An IOCTL_SERIAL_SET_TIMEOUTS request resets the time-out value that the system-supplied bus driver for parallel ports uses with write requests.
old-location : parports\ioctl_serial_set_timeouts.htm
old-project : parports
ms.assetid : 524efbe1-110e-4c59-a759-b083888b2e26
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : parports.ioctl_serial_set_timeouts, IOCTL_SERIAL_SET_TIMEOUTS control code [Parallel Ports], IOCTL_SERIAL_SET_TIMEOUTS, ntddser/IOCTL_SERIAL_SET_TIMEOUTS, cisspd_d42d38bf-b276-4428-9a6e-05f4d0b4253b.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ntddser.h
req.include-header : Ntddser.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_SET_TIMEOUTS IOCTL
An IOCTL_SERIAL_SET_TIMEOUTS request resets the time-out value that the system-supplied bus driver for parallel ports uses with write requests. The write time-out value is used with SPP and SW_ECP modes. The parallel port bus driver queues a set time-out request on a work queue for the parallel device.

A client uses an <a href="..\ntddser\ni-ntddser-ioctl_serial_get_timeouts.md">IOCTL_SERIAL_GET_TIMEOUTS</a> to obtain the time-out values.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The <b>AssociatedIrp.SystemBuffer</b> points to a SERIAL_TIMEOUTS structure that the client allocates to input time-out information. The client sets the <b>WriteTotalTimeoutConstant</b> member to a value in milliseconds.

### Input Buffer Length
The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a SERIAL_TIMEOUTS structure.

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

The <b>Status</b> member is set to one of the generic status values returned by device control requests for parallel devices or to one of the following values:


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddser.h (include Ntddser.h) |

## See Also

<a href="..\ntddser\ni-ntddser-ioctl_serial_get_timeouts.md">IOCTL_SERIAL_GET_TIMEOUTS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20IOCTL_SERIAL_SET_TIMEOUTS control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>