---
UID : NI:ntddcdrm.IOCTL_CDROM_STOP_AUDIO
title : IOCTL_CDROM_STOP_AUDIO
author : windows-driver-content
description : Ends audio play. Obsolete, beginning with Windows Vista.
old-location : storage\ioctl_cdrom_stop_audio.htm
old-project : storage
ms.assetid : 9d250950-7ecf-4433-9aaf-7696abb5b66c
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _WRITE_ROTATION, WRITE_ROTATION, *PWRITE_ROTATION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ntddcdrm.h
req.include-header : Ntddcdrm.h
req.target-type : Windows
req.target-min-winverclnt : Obsolete, beginning with Windows Vista.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IOCTL_CDROM_STOP_AUDIO
req.alt-loc : ntddcdrm.h
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
req.typenames : WRITE_ROTATION, *PWRITE_ROTATION
---

# IOCTL_CDROM_STOP_AUDIO IOCTL
Ends audio play.  Obsolete, beginning with Windows Vista.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
I/O Status block
The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST if audio is not currently playing, STATUS_IO_DEVICE_ERROR, STATUS_NO_MEDIA_IN_DEVICE, STATUS_DEVICE_NOT_READY, STATUS_IO_TIME_OUT, or STATUS_VERIFY_REQUIRED.

    ## Remarks
        Beginning with Windows Vista, CDROM class drivers do not use this IOCTL. Prior to Windows Vista, this IOCTL was used for audio playback on older CD-ROM drives that supported direct audio output in hardware.

Client applications should use the <i>Media Control Interface (MCI) API</i> rather than issuing this IOCTL.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |
| **IRQL** |  |