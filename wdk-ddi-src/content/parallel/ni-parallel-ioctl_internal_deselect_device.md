---
UID : NI:parallel.IOCTL_INTERNAL_DESELECT_DEVICE
title : IOCTL_INTERNAL_DESELECT_DEVICE
author : windows-driver-content
description : The IOCTL_INTERNAL_DESELECT_DEVICE request deselects an IEEE 1284.3 daisy-chain device or an IEEE 1284 end-of-chain device attached to a parallel port.
old-location : parports\ioctl_internal_deselect_device.htm
old-project : parports
ms.assetid : 39cb818e-6219-4d7e-8114-8c0dfdfff76e
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : parports.ioctl_internal_deselect_device, IOCTL_INTERNAL_DESELECT_DEVICE control code [Parallel Ports], IOCTL_INTERNAL_DESELECT_DEVICE, parallel/IOCTL_INTERNAL_DESELECT_DEVICE, cisspd_8ade9861-f2cd-4328-9f8a-92fa4b2d2163.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : parallel.h
req.include-header : Parallel.h
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
req.typenames : RILGBATOKEN, *LPRILGBATOKEN
---

# IOCTL_INTERNAL_DESELECT_DEVICE IOCTL
The <b>IOCTL_INTERNAL_DESELECT_DEVICE</b> request deselects an IEEE 1284.3 daisy-chain device or an IEEE 1284 end-of-chain device attached to a parallel port.

For more information, see <a href="https://msdn.microsoft.com/1a3ac1b1-9180-4b71-8740-70c6fbe9a885">Selecting and Deselecting an IEEE 1284 Device Attached to a ParallelPort</a>.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a <a href="..\parallel\ns-parallel-_parallel_1284_command.md">PARALLEL_1284_COMMAND</a> structure that the client allocates to input IEEE 1284.3 command information. The client can free the parallel port by not setting the PAR_HAVE_PORT_KEEP_PORT flag in the <b>CommandFlags</b> member.

### Input Buffer Length
The <b>Parameters.DeviceIoControl.InputBufferLength</b> member specifies the size, in bytes, of the PARALLEL_1284_COMMAND structure.

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

The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports or to one of the following values:


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | parallel.h (include Parallel.h) |

## See Also

<a href="..\parallel\ni-parallel-ioctl_internal_select_device.md">IOCTL_INTERNAL_SELECT_DEVICE</a>

<a href="..\parallel\ns-parallel-_parallel_1284_command.md">PARALLEL_1284_COMMAND</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20IOCTL_INTERNAL_DESELECT_DEVICE control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>