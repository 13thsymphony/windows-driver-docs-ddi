---
UID : NI:mountdev.IOCTL_MOUNTDEV_LINK_DELETED
title : IOCTL_MOUNTDEV_LINK_DELETED
author : windows-driver-content
description : Support for this IOCTL by the mount manager clients is optional. It alerts the mount manager client that a persistent name associated with it has been deleted. The input for this IOCTL is the persistent name that was deleted.
old-location : storage\ioctl_mountdev_link_deleted.htm
old-project : storage
ms.assetid : 6fd0696d-5b8d-4502-bbdb-a013bee2e9d4
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ioctl_mountdev_link_deleted, IOCTL_MOUNTDEV_LINK_DELETED control code [Storage Devices], IOCTL_MOUNTDEV_LINK_DELETED, mountdev/IOCTL_MOUNTDEV_LINK_DELETED, k307_b0ab5504-dac9-410f-bb73-bbb5876e4a59.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : mountdev.h
req.include-header : Mountmgr.h
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
req.typenames : ZONE_DESCRIPTIOR, *PZONE_DESCRIPTIOR
---

# IOCTL_MOUNTDEV_LINK_DELETED IOCTL
Support for this IOCTL by the mount manager clients is optional. It alerts the mount manager client that a persistent name associated with it has been deleted. The input for this IOCTL is the persistent name that was deleted.

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
| **Windows Driver kit version** |  |
| **Header** | mountdev.h (include Mountmgr.h) |
| **IRQL** |  |

## See Also

<a href="..\mountmgr\ns-mountmgr-_mountdev_name.md">MOUNTDEV_NAME</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_MOUNTDEV_LINK_DELETED control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>