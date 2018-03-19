---
UID: NI:ntddcdrm.IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX
title: IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX
author: windows-driver-content
description: Returns information about a CD-ROM's geometry (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).The IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX request differs from the older IOCTL_CDROM_GET_DRIVE_GEOMETRY request.
old-location: storage\ioctl_cdrom_get_drive_geometry_ex.htm
old-project: storage
ms.assetid: ef04ba90-698f-4ae2-9ac6-106d66b61080
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX, IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX control code [Storage Devices], k307_d92083df-7f01-4858-8bab-5b4b4ea5eaea.xml, ntddcdrm/IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX, storage.ioctl_cdrom_get_drive_geometry_ex
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
-	IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX
product: Windows
targetos: Windows
req.typenames: WRITE_ROTATION, *PWRITE_ROTATION
---

# IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX IOCTL
Returns information about a CD-ROM's geometry (media type, number of cylinders, tracks per cylinder, sectors per track, and bytes per sector).

The IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX request differs from the older <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_drive_geometry.md">IOCTL_CDROM_GET_DRIVE_GEOMETRY</a> request. The IOCTL_CDROM_GET_DRIVE_GEOMETRY_EX request can retrieve information from both Master Boot Record (MBR) and GUID Partition Table (GPT) partitioned media. However, IOCTL_CDROM_GET_DRIVE_GEOMETRY can read only MBR-style media.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
The driver returns the <a href="..\ntdddisk\ns-ntdddisk-_disk_geometry_ex.md">DISK_GEOMETRY_EX</a>-type information in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

### Output Buffer Length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the IO_STACK_LOCATION structure of the IRP indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(DISK_GEOMETRY_EX).

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to the size, in bytes, of the returned data. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_UNRECOGNIZED_MEDIA, STATUS_INVALID_PARAMETER, STATUS_INFO_LENGTH_MISMATCH, or STATUS_BUFFER_TOO_SMALL.

## Remarks
TBD

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntdddisk\ns-ntdddisk-_disk_geometry_ex.md">DISK_GEOMETRY_EX</a>



<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_drive_geometry_ex.md">IOCTL_DISK_GET_DRIVE_GEOMETRY_EX</a>