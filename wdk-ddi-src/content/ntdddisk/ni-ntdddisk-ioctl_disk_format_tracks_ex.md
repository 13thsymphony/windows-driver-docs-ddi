---
UID : NI:ntdddisk.IOCTL_DISK_FORMAT_TRACKS_EX
title : IOCTL_DISK_FORMAT_TRACKS_EX
author : windows-driver-content
description : Is similar to IOCTL_DISK_FORMAT_TRACKS, except that it allows the caller to specify several more parameters.
old-location : storage\ioctl_disk_format_tracks_ex.htm
old-project : storage
ms.assetid : 6bd7e722-6603-4d3b-9f18-1b7eb531f5fb
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ioctl_disk_format_tracks_ex, IOCTL_DISK_FORMAT_TRACKS_EX control code [Storage Devices], IOCTL_DISK_FORMAT_TRACKS_EX, ntdddisk/IOCTL_DISK_FORMAT_TRACKS_EX, k307_b3ebee51-e107-493e-b2dc-1457b4b39670.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ntdddisk.h
req.include-header : Ntdddisk.h
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
req.typenames : DETECTION_TYPE
---

# IOCTL_DISK_FORMAT_TRACKS_EX IOCTL
Is similar to <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_format_tracks.md">IOCTL_DISK_FORMAT_TRACKS</a>, except that it allows the caller to specify several more parameters. The additional extended parameters are the format gap length, the number of sectors per track, and an array whose element size is equal to the number of sectors per track. This array represents the track layout.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the <a href="..\ntdddisk\ns-ntdddisk-_format_ex_parameters.md">FORMAT_EX_PARAMETERS</a> data.

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

<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_format_tracks.md">IOCTL_DISK_FORMAT_TRACKS</a>

<a href="..\ntdddisk\ns-ntdddisk-_format_ex_parameters.md">FORMAT_EX_PARAMETERS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_DISK_FORMAT_TRACKS_EX control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>