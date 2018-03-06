---
UID: NI:ntddcdrm.IOCTL_CDROM_GET_DRIVE_GEOMETRY
title: IOCTL_CDROM_GET_DRIVE_GEOMETRY
author: windows-driver-content
description: Returns information about the CD-ROM's geometry (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).
old-location: storage\ioctl_cdrom_get_drive_geometry.htm
old-project: storage
ms.assetid: ed9738cb-7016-417b-baae-b8d4242a384e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_CDROM_GET_DRIVE_GEOMETRY, IOCTL_CDROM_GET_DRIVE_GEOMETRY control code [Storage Devices], k307_f082c6e5-9d9a-4a11-a363-710f30cf3881.xml, ntddcdrm/IOCTL_CDROM_GET_DRIVE_GEOMETRY, storage.ioctl_cdrom_get_drive_geometry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
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
-	ntddcdrm.h
api_name:
-	IOCTL_CDROM_GET_DRIVE_GEOMETRY
product: Windows
targetos: Windows
req.typenames: WRITE_ROTATION, *PWRITE_ROTATION
---

# IOCTL_CDROM_GET_DRIVE_GEOMETRY IOCTL
Returns information about the CD-ROM's geometry (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
The driver returns the <a href="..\ntdddisk\ns-ntdddisk-_disk_geometry.md">DISK_GEOMETRY</a>-type information in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

### Output Buffer Length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(DISK_GEOMETRY).

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_drive_geometry_ex.md">IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX</a>



<a href="..\ntdddisk\ns-ntdddisk-_disk_geometry.md">DISK_GEOMETRY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CDROM_GET_DRIVE_GEOMETRY control code%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>