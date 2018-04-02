---
UID: NI:ntdddisk.IOCTL_DISK_GET_DRIVE_LAYOUT_EX
title: IOCTL_DISK_GET_DRIVE_LAYOUT_EX
author: windows-driver-content
description: Returns information about the number of partitions, disk signature, and features of each partition on a disk. (Floppy drivers need not handle this request.).
old-location: storage\ioctl_disk_get_drive_layout_ex.htm
old-project: storage
ms.assetid: b0ffd1a6-aaa1-4001-a02b-6c0693b7ec5c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_DISK_GET_DRIVE_LAYOUT_EX, IOCTL_DISK_GET_DRIVE_LAYOUT_EX control code [Storage Devices], k307_81993d9b-900f-412c-ac07-f0765114141f.xml, ntdddisk/IOCTL_DISK_GET_DRIVE_LAYOUT_EX, storage.ioctl_disk_get_drive_layout_ex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
-	Ntdddisk.h
api_name:
-	IOCTL_DISK_GET_DRIVE_LAYOUT_EX
product:
- Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_GET_DRIVE_LAYOUT_EX IOCTL
Returns information about the number of partitions, disk signature, and features of each partition on a disk. (Floppy drivers need not handle this request.)

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
The driver returns the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552662">DRIVE_LAYOUT_INFORMATION_EX</a> data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

### Output Buffer Length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(DRIVE_LAYOUT_INFORMATION_EX). Note that this structure contains a variable-sized array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563754">PARTITION_INFORMATION_EX</a> elements.

To determine the size of output buffer that is required, caller should send this IOCTL request in a loop. Every time the storage stack rejects the IOCTL with an error message indicating that the buffer was too small, caller should double the buffer size.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to the size, in bytes, of the returned data. The <b>Status</b> field can be set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, or STATUS_BUFFER_TOO_SMALL.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntdddisk.h (include Ntdddisk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552659">DRIVE_LAYOUT_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563751">PARTITION_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563754">PARTITION_INFORMATION_EX</a>