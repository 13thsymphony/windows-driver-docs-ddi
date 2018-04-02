---
UID: NI:ntdddisk.IOCTL_DISK_FORMAT_TRACKS_EX
title: IOCTL_DISK_FORMAT_TRACKS_EX
author: windows-driver-content
description: Is similar to IOCTL_DISK_FORMAT_TRACKS, except that it allows the caller to specify several more parameters.
old-location: storage\ioctl_disk_format_tracks_ex.htm
old-project: storage
ms.assetid: 6bd7e722-6603-4d3b-9f18-1b7eb531f5fb
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_DISK_FORMAT_TRACKS_EX, IOCTL_DISK_FORMAT_TRACKS_EX control code [Storage Devices], k307_b3ebee51-e107-493e-b2dc-1457b4b39670.xml, ntdddisk/IOCTL_DISK_FORMAT_TRACKS_EX, storage.ioctl_disk_format_tracks_ex
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
-	IOCTL_DISK_FORMAT_TRACKS_EX
product:
- Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_FORMAT_TRACKS_EX IOCTL
Is similar to <a href="https://msdn.microsoft.com/library/windows/hardware/ff559447">IOCTL_DISK_FORMAT_TRACKS</a>, except that it allows the caller to specify several more parameters. The additional extended parameters are the format gap length, the number of sectors per track, and an array whose element size is equal to the number of sectors per track. This array represents the track layout.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553875">FORMAT_EX_PARAMETERS</a> data.

### Input Buffer Length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer.

### Output Buffer
The device driver returns an array of BAD_TRACK_NUMBER values to the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. BAD_TRACK_NUMBER is currently defined as a WORD on 32-bit systems.

### Output Buffer Length
Length of the buffer.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The driver sets the <b>Status</b> field to STATUS_SUCCESS. Otherwise, the driver sets the <b>Status</b> field to STATUS_INVALID_PARAMETER if the input buffer length is &lt; <b>sizeof</b>(FORMAT_EX_PARAMETERS) or if the format parameters supplied by the caller will not work on the drive to be formatted.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntdddisk.h (include Ntdddisk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553875">FORMAT_EX_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559447">IOCTL_DISK_FORMAT_TRACKS</a>