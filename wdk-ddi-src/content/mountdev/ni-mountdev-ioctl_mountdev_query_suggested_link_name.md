---
UID : NI:mountdev.IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME
title : IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME
author : windows-driver-content
description : Support for this IOCTL by the mount manager clients is optional.
old-location : storage\ioctl_mountdev_query_suggested_link_name.htm
old-project : storage
ms.assetid : 4afd8c7a-b7b4-4a02-a270-d4e29f5329f9
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ioctl_mountdev_query_suggested_link_name, IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME control code [Storage Devices], IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME, mountdev/IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME, k307_90b74e7c-57f6-4738-8a5e-d947c29c5aab.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : mountdev.h
req.include-header : Mountdev.h
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
req.typenames : "*PZONE_DESCRIPTIOR, ZONE_DESCRIPTIOR"
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
The client driver must place a variable-length structure of type <a href="..\mountdev\ns-mountdev-_mountdev_suggested_link_name.md">MOUNTDEV_SUGGESTED_LINK_NAME</a>, defined in <i>moundev.h</i>, at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. Starting at the address of the structure member <i>Name</i>, the client driver must insert the suggested persistent name.

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
| **Windows Driver kit version** |  |
| **Header** | mountdev.h (include Mountdev.h) |
| **IRQL** |  |

## See Also

<a href="..\mountdev\ns-mountdev-_mountdev_suggested_link_name.md">MOUNTDEV_SUGGESTED_LINK_NAME</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>