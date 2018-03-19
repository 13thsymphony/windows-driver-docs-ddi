---
UID: NI:mountmgr.IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_CREATED
title: IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_CREATED
author: windows-driver-content
description: This IOCTL alerts the mount manager that a volume mount point has been created, so that the mount manager can replicate the database entry for the given mount point.
old-location: storage\ioctl_mountmgr_volume_mount_point_created.htm
old-project: storage
ms.assetid: 6042916a-1f0e-48ff-b73b-a37974281f96
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_CREATED, IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_CREATED control code [Storage Devices], k307_939215e3-3e33-401e-a1d4-c8d82b68f0e8.xml, mountmgr/IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_CREATED, storage.ioctl_mountmgr_volume_mount_point_created
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: mountmgr.h
req.include-header: Mountmgr.h
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
-	Mountmgr.h
api_name:
-	IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_CREATED
product: Windows
targetos: Windows
req.typenames: MOUNTDEV_UNIQUE_ID, *PMOUNTDEV_UNIQUE_ID
---

# IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_CREATED IOCTL
This IOCTL alerts the mount manager that a volume mount point has been created, so that the mount manager can replicate the database entry for the given mount point. Its primary function is to allow volume mount points to persist even when the volumes are moved from one system to another.

The Microsoft Win32 routine <b>SetVolumeMountPoint</b> sends this IOCTL to the mount manager, to inform the mount manager that a newly-created directory junction is pointing to a volume name. The mount manager responds by storing the volume name contained in the directory junction along with its unique ID on the volume hosting the directory junction.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The mount manager client initializes the <a href="..\mountmgr\ns-mountmgr-_mountmgr_volume_mount_point.md">MOUNTMGR_VOLUME_MOUNT_POINT</a> structure, defined in <i>Mountmgr.h</i>, at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

### Input Buffer Length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(MOUNTMGR_VOLUME_MOUNT_POINT).

### Output Buffer
None

### Output Buffer Length
None

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.

If <b>InputBufferLength</b> is less than <b>sizeof</b>(MOUNTMGR_VOLUME_MOUNT_POINT), the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | mountmgr.h (include Mountmgr.h) |

## See Also

<a href="..\mountmgr\ns-mountmgr-_mountmgr_volume_mount_point.md">MOUNTMGR_VOLUME_MOUNT_POINT</a>