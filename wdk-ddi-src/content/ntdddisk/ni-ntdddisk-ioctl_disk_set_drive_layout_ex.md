---
UID: NI:ntdddisk.IOCTL_DISK_SET_DRIVE_LAYOUT_EX
title: IOCTL_DISK_SET_DRIVE_LAYOUT_EX
author: windows-driver-content
description: Repartitions a disk as specified. (Floppy drivers need not handle this request.).
old-location: storage\ioctl_disk_set_drive_layout_ex.htm
old-project: storage
ms.assetid: ef0da533-4514-4de4-a4d2-8a0f1b5de12f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_DISK_SET_DRIVE_LAYOUT_EX, IOCTL_DISK_SET_DRIVE_LAYOUT_EX control code [Storage Devices], k307_4f25801a-eda0-42b1-9969-47f01f39c3fb.xml, ntdddisk/IOCTL_DISK_SET_DRIVE_LAYOUT_EX, storage.ioctl_disk_set_drive_layout_ex
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
-	IOCTL_DISK_SET_DRIVE_LAYOUT_EX
product: Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_SET_DRIVE_LAYOUT_EX IOCTL
Repartitions a disk as specified. (Floppy drivers need not handle this request.)

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552662">DRIVE_LAYOUT_INFORMATION_EX</a> values to be set.

### Input Buffer Length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(DRIVE_LAYOUT_INFORMATION_EX).

### Output Buffer
Returns updated DRIVE_LAYOUT_INFORMATION_EX, possibly with modified partition numbers, to the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

### Output Buffer Length
Length of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552662">DRIVE_LAYOUT_INFORMATION_EX</a>.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to the size, in bytes, of the returned information. The <b>Status</b> field can be set to STATUS_SUCCESS, or possibly to STATUS_INVALID_PARAMETER, STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, or STATUS_BUFFER_TOO_SMALL.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntdddisk.h (include Ntdddisk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552662">DRIVE_LAYOUT_INFORMATION_EX</a>