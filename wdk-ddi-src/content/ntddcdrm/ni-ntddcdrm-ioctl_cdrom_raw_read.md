---
UID: NI:ntddcdrm.IOCTL_CDROM_RAW_READ
title: IOCTL_CDROM_RAW_READ
author: windows-driver-content
description: Reads data from the CD-ROM in raw mode.
old-location: storage\ioctl_cdrom_raw_read.htm
old-project: storage
ms.assetid: b7791cf7-476c-4319-976d-9da3d96b6a76
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_cdrom_raw_read, IOCTL_CDROM_RAW_READ control code [Storage Devices], IOCTL_CDROM_RAW_READ, ntddcdrm/IOCTL_CDROM_RAW_READ, k307_1c2f1a05-940c-40f8-a280-3a23d3bb4171.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddcdrm.h
apiname:
-	IOCTL_CDROM_RAW_READ
product: Windows
targetos: Windows
req.typenames: WRITE_ROTATION, *PWRITE_ROTATION
---

# IOCTL_CDROM_RAW_READ IOCTL
Reads data from the CD-ROM in raw mode.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
If the IOCTL is from user mode, <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="..\ntddcdrm\ns-ntddcdrm-__raw_read_info.md">RAW_READ_INFO</a> structure that specifies the starting disk offset, the sector count, and the track mode (XA or CDDA) for the read. <b>Parameters.DeviceIoControl.InputBufferLength</b> specifies the size, in bytes, of the structure, which must be &gt;= <b>sizeof</b>(RAW_READ_INFO). <b>Parameters.DeviceIoControl.OutputBufferLength</b> specifies the size of the buffer to be read, which must be &gt;= <b>sizeof</b>(<i>SectorCount</i> * RAW_SECTOR_SIZE).

If the IOCTL is from kernel mode, <b>Parameters.DeviceIoControl.Type3InputBuffer</b> contains a structure that specifies the starting disk offset, the sector count, and the track mode (XA or CDDA) for the read. <b>Parameters.DeviceIoControl.OutputBufferLength</b> specifies the size of the buffer, in bytes, to be read, which must be &gt;= <b>sizeof</b>(<i>SectorCount</i> * RAW_SECTOR_SIZE).

### Input Buffer Length
See above.

### Output Buffer
The driver writes the requested bytes directly (using DMA or PIO) to the buffer described by the MDL at <b>Irp-&gt;MdlAddress</b>.

### Output Buffer Length
Length of an MDL.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the read is successful, the driver sets <b>Status</b> to STATUS_SUCCESS and <b>Information</b> to the number of bytes transferred. If the read is not successful, the driver sets <b>Information</b> to zero and <b>Status</b> to possibly STATUS_INVALID_PARAMETER, STATUS_INSUFFICIENT_RESOURCES, or STATUS_INVALID_DEVICE_REQUEST.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddcdrm\ns-ntddcdrm-__raw_read_info.md">RAW_READ_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CDROM_RAW_READ control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>