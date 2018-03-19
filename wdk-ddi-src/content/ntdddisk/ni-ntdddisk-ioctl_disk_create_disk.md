---
UID: NI:ntdddisk.IOCTL_DISK_CREATE_DISK
title: IOCTL_DISK_CREATE_DISK
author: windows-driver-content
description: Creates an empty partition for the device object.
old-location: storage\ioctl_disk_create_disk.htm
old-project: storage
ms.assetid: 9ec6835c-43b8-4878-9ddf-1ca7c24435c2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_DISK_CREATE_DISK, IOCTL_DISK_CREATE_DISK control code [Storage Devices], k307_1520ab81-e89f-4531-a6ac-0998e1b1b658.xml, ntdddisk/IOCTL_DISK_CREATE_DISK, storage.ioctl_disk_create_disk
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
-	IOCTL_DISK_CREATE_DISK
product: Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_CREATE_DISK IOCTL
Creates an empty partition for the device object. It can operate on either an EFI disk or an MBR disk. The parameters necessary to create an empty disk depend on the type of partition table that will be put onto the disk. For more information, see <a href="..\ntdddisk\ns-ntdddisk-_create_disk.md">CREATE_DISK</a>.

Disk drivers enumerate partitions as though they were child devices. Thus, upon creating the new partition, the disk class driver notifies the PnP manager by means of a call to <b>IoInvalidateDeviceRelations</b> that the disk device has a new child device (partition).

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the CREATE_DISK data.

### Input Buffer Length
<b>
       Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer made available to the driver, which must be &gt;= <b>sizeof</b>(CREATE_DISK). Otherwise, the driver returns with an error status of STATUS_INFO_LENGTH_MISMATCH.

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS if the operation was successful. Other possible status values are: STATUS_NOT_SUPPORTED if the partition style requested is not supported; STATUS_DEVICE_NOT_READY if the class driver failed to retrieve the disk geometry; and STATUS_INSUFFICIENT_RESOURCES if the class driver failed to obtain a necessary resource, such as heap memory.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntdddisk.h (include Ntdddisk.h) |

## See Also

<a href="..\ntdddisk\ns-ntdddisk-_create_disk.md">CREATE_DISK</a>