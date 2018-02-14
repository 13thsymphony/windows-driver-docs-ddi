---
UID: NI:ntdddisk.IOCTL_DISK_GROW_PARTITION
title: IOCTL_DISK_GROW_PARTITION
author: windows-driver-content
description: Increases the size of an existing partition.
old-location: storage\ioctl_disk_grow_partition.htm
old-project: storage
ms.assetid: 984e9e7a-c135-4a6a-973d-b8597d9f8fed
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_disk_grow_partition, IOCTL_DISK_GROW_PARTITION control code [Storage Devices], IOCTL_DISK_GROW_PARTITION, ntdddisk/IOCTL_DISK_GROW_PARTITION, k307_f3c07ac5-6895-46f9-85ad-7706661164a1.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntdddisk.h
apiname:
-	IOCTL_DISK_GROW_PARTITION
product: Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_GROW_PARTITION IOCTL
Increases the size of an existing partition. It is used in conjunction with <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_update_drive_size.md">IOCTL_DISK_UPDATE_DRIVE_SIZE</a> to extend a disk, so that it will contain a new free space area, and then to extend an existing partition on the disk into the newly attached free space. It takes a <a href="..\ntdddisk\ns-ntdddisk-_disk_grow_partition.md">DISK_GROW_PARTITION</a> structure as the only parameter. For this operation to work, the space after the specified partition must be free. A partition cannot be extended over another existing partition.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the <a href="..\ntdddisk\ns-ntdddisk-_disk_grow_partition.md">DISK_GROW_PARTITION</a> values - that will be used to increase the size of the partition.

### Input Buffer Length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer made available to the driver, which must be &gt;= <b>sizeof</b>(DISK_GROW_PARTITION). Otherwise, the driver returns with an error status of STATUS_BUFFER_TOO_SMALL.

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL, STATUS_INVALID_PARAMETER, STATUS_UNSUCCESSFUL, or STATUS_DRIVER_INTERNAL_ERROR.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntdddisk.h (include Ntdddisk.h) |

## See Also

<a href="..\ntdddisk\ns-ntdddisk-_disk_grow_partition.md">DISK_GROW_PARTITION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_DISK_GROW_PARTITION control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>