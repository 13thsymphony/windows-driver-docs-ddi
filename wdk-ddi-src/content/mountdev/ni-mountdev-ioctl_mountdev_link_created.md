---
UID: NI:mountdev.IOCTL_MOUNTDEV_LINK_CREATED
title: IOCTL_MOUNTDEV_LINK_CREATED
author: windows-driver-content
description: Support for this IOCTL by the mount manager clients is optional. The mount manager uses this IOCTL to alert the client driver that a persistent name has been assigned to its volume. The input for this IOCTL is the persistent name assigned.
old-location: storage\ioctl_mountdev_link_created.htm
old-project: storage
ms.assetid: 98ccf623-8232-4bcb-bd72-39dd31c7ede3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.ioctl_mountdev_link_created, IOCTL_MOUNTDEV_LINK_CREATED control code [Storage Devices], IOCTL_MOUNTDEV_LINK_CREATED, mountdev/IOCTL_MOUNTDEV_LINK_CREATED, k307_b93a8e67-8e02-4d7d-aac2-a11f3d4297c2.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: mountdev.h
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
-	mountdev.h
apiname:
-	IOCTL_MOUNTDEV_LINK_CREATED
product: Windows
targetos: Windows
req.typenames: ZONE_DESCRIPTIOR, *PZONE_DESCRIPTIOR
---

# IOCTL_MOUNTDEV_LINK_CREATED IOCTL
Support for this IOCTL by the mount manager clients is optional. The mount manager uses this IOCTL to alert the client driver that a persistent name has been assigned to its volume. The input for this IOCTL is the persistent name assigned.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The mount point manager places a variable-length structure of type <a href="..\mountmgr\ns-mountmgr-_mountdev_name.md">MOUNTDEV_NAME</a>, defined in <i>Mountmgr.h</i>, at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. The mount manager inserts the persistent name just assigned at the address pointed to by the <i>Name</i> member of this structure.

### Input Buffer Length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(MOUNTDEV_NAME).

### Output Buffer
None

### Output Buffer Length
None

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
No status.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | mountdev.h (include Mountmgr.h) |

## See Also

<a href="..\mountmgr\ns-mountmgr-_mountdev_name.md">MOUNTDEV_NAME</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_MOUNTDEV_LINK_CREATED control code%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>