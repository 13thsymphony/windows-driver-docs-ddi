---
UID: NI:mountdev.IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME
title: IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME
author: windows-driver-content
description: Support for this IOCTL by the mount manager clients is optional.
old-location: storage\ioctl_mountdev_query_suggested_link_name.htm
old-project: storage
ms.assetid: 4afd8c7a-b7b4-4a02-a270-d4e29f5329f9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME, IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME control code [Storage Devices], k307_90b74e7c-57f6-4738-8a5e-d947c29c5aab.xml, mountdev/IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME, storage.ioctl_mountdev_query_suggested_link_name
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: mountdev.h
req.include-header: Mountdev.h
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
-	Mountdev.h
api_name:
-	IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME
product:
- Windows
targetos: Windows
req.typenames: ZONE_DESCRIPTIOR, *PZONE_DESCRIPTIOR
---

# IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME IOCTL
Support for this IOCTL by the mount manager clients is optional. Some mount manager clients are able to keep track of their drive letters across reboots of the system without the help of the mount manager. Such clients can send a suggested drive letter name to the mount manager in response to this IOCTL. The mount manager uses the suggested name if the mount manager's database does not already contain a persistent drive letter name for the client's volume. Otherwise, it ignores the suggestion and uses the drive letter name in its persistent name database.

Drive letter names must include the full path of the symbolic link in object namespace and must have the traditional MS-DOS syntax. For instance, drive letter "D" must be represented in this manner: "\DosDevices\D:". The alternative symbolic link path of "\??\D:" may not be used, nor may abbreviations of the symbolic link such as "D:".

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<text></text>

### Input Buffer Length
<text></text>

### Output Buffer
The client driver must place a variable-length structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff562258">MOUNTDEV_SUGGESTED_LINK_NAME</a>, defined in <i>moundev.h</i>, at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. Starting at the address of the structure member <i>Name</i>, the client driver must insert the suggested persistent name.

### Output Buffer Length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer, which must be greater than or equal to <b>sizeof</b>(MOUNTDEV_SUGGESTED_LINK_NAME).

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the operation is successful, the <b>Information</b> field is set to the total number of bytes returned and the <b>Status</b> field is set to STATUS_SUCCESS.

If <b>OutputBufferLength</b> is less than <b>sizeof</b>(MOUNTDEV_SUGGESTED_LINK_NAME), the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.

If <b>OutputBufferLength</b> is less than the total length of output data, the <b>Status</b> field is set to STATUS_BUFFER_OVERFLOW and the <b>Information</b> field is set to <b>sizeof</b>(MOUNTDEV_SUGGESTED_LINK_NAME).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | mountdev.h (include Mountdev.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562258">MOUNTDEV_SUGGESTED_LINK_NAME</a>