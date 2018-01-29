---
UID : NI:ntddcdrm.IOCTL_CDROM_SEEK_AUDIO_MSF
title : IOCTL_CDROM_SEEK_AUDIO_MSF
author : windows-driver-content
description : Moves the heads to the specified MSF on the media. Obsolete, beginning with Windows Vista.
old-location : storage\ioctl_cdrom_seek_audio_msf.htm
old-project : storage
ms.assetid : 081a5d8d-7cc7-4499-9360-dfaa5a7c436b
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ioctl_cdrom_seek_audio_msf, IOCTL_CDROM_SEEK_AUDIO_MSF control code [Storage Devices], IOCTL_CDROM_SEEK_AUDIO_MSF, ntddcdrm/IOCTL_CDROM_SEEK_AUDIO_MSF, k307_4c88dbd2-30ef-41aa-9330-57319605ec88.xml
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
req.typenames : WRITE_ROTATION, *PWRITE_ROTATION
---

# IOCTL_CDROM_SEEK_AUDIO_MSF IOCTL
Moves the heads to the specified MSF on the media.  Obsolete, beginning with Windows Vista.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i> contains the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_seek_audio_msf.md">CDROM_SEEK_AUDIO_MSF</a> specification.

### Input Buffer Length
<i>Parameters.DeviceIoControl.InputBufferLength</i> indicates the size, in bytes, of the buffer.

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL, STATUS_INVALID_DEVICE_REQUEST, STATUS_IO_DEVICE_ERROR, STATUS_NO_MEDIA_IN_DEVICE, STATUS_DEVICE_NOT_READY, STATUS_IO_TIME_OUT, or STATUS_VERIFY_REQUIRED.

## Remarks
Beginning with Windows Vista, CDROM class drivers do not use this IOCTL. Prior to Windows Vista, this IOCTL was used for audio playback on older CD-ROM drives that supported direct audio output in hardware.

Client applications should use the <i>Media Control Interface (MCI) API</i> rather than issuing this IOCTL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |
| **IRQL** |  |

## See Also

<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_seek_audio_msf.md">CDROM_SEEK_AUDIO_MSF</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CDROM_SEEK_AUDIO_MSF control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>