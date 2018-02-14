---
UID: NI:mountmgr.IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_DELETED
title: IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_DELETED
author: windows-driver-content
description: The mount manager clients use this IOCTL to alert the mount manager that a volume mount point has been deleted so that the mount manager can replicate the database entry for the given mount point.
old-location: storage\ioctl_mountmgr_volume_mount_point_deleted.htm
old-project: storage
ms.assetid: 8a436053-87c2-4fa2-9280-7035a990d0b4
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_mountmgr_volume_mount_point_deleted, IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_DELETED control code [Storage Devices], IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_DELETED, mountmgr/IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_DELETED, k307_fce8de67-6c3d-4e89-8259-a7058c968c62.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Mountmgr.h
apiname:
-	IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_DELETED
product: Windows
targetos: Windows
req.typenames: "*PMOUNTDEV_UNIQUE_ID, MOUNTDEV_UNIQUE_ID"
---

# IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_DELETED IOCTL
The mount manager clients use this IOCTL to alert the mount manager that a volume mount point has been deleted so that the mount manager can replicate the database entry for the given mount point.

The Microsoft Win32 routine <b>DeleteVolumeMountPoint</b> sends this IOCTL to the mount manager, to inform the mount manager that a directory junction is no longer pointing to a volume name. The mount manager responds by deleting the volume name formerly contained in the directory junction along with its unique ID from the volume hosting the directory junction.

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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_DELETED control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>