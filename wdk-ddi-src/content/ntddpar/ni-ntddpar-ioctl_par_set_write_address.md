---
UID: NI:ntddpar.IOCTL_PAR_SET_WRITE_ADDRESS
title: IOCTL_PAR_SET_WRITE_ADDRESS
author: windows-driver-content
description: The IOCTL_PAR_SET_WRITE_ADDRESS request sets an extended capabilities port (ECP) or enhanced parallel port (EPP) write address (channel) for a parallel device. The parallel port bus driver queues this request on a work queue for the parallel device.
old-location: parports\ioctl_par_set_write_address.htm
old-project: parports
ms.assetid: ea4a071e-aa6b-4c9f-b497-523af7e42430
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_PAR_SET_WRITE_ADDRESS, IOCTL_PAR_SET_WRITE_ADDRESS control code [Parallel Ports], cisspd_396ff93f-623f-48a5-925e-9338672fa974.xml, ntddpar/IOCTL_PAR_SET_WRITE_ADDRESS, parports.ioctl_par_set_write_address
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddpar.h
req.include-header: Ntddpar.h
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
-	ntddpar.h
api_name:
-	IOCTL_PAR_SET_WRITE_ADDRESS
product:
- Windows
targetos: Windows
req.typenames: OFFLOAD_SECURITY_ASSOCIATION, *POFFLOAD_SECURITY_ASSOCIATION
---

# IOCTL_PAR_SET_WRITE_ADDRESS IOCTL
The IOCTL_PAR_SET_WRITE_ADDRESS request sets an extended capabilities port (ECP) or enhanced parallel port (EPP) write address (channel) for a parallel device. The parallel port bus driver queues this request on a work queue for the parallel device.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a UCHAR buffer that the client allocates to input a write address. The client sets the buffer to an ECP or EPP write address.

### Input Buffer Length
<b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a UCHAR.

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

The <b>Status</b> member is set to one of the generic status values returned by device control requests for parallel devices or to the following value:


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddpar.h (include Ntddpar.h) |

## See Also

<a href="..\ntddpar\ni-ntddpar-ioctl_par_set_read_address.md">IOCTL_PAR_SET_READ_ADDRESS</a>