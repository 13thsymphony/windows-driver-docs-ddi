---
UID: NI:ntddcdrm.IOCTL_CDROM_READ_TOC
title: IOCTL_CDROM_READ_TOC
author: windows-driver-content
description: Returns the table of contents of the media. Obsolete, beginning with Windows Vista.
old-location: storage\ioctl_cdrom_read_toc.htm
old-project: storage
ms.assetid: 4820dca5-7bbe-425d-9063-54450146f273
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.ioctl_cdrom_read_toc, IOCTL_CDROM_READ_TOC control code [Storage Devices], IOCTL_CDROM_READ_TOC, ntddcdrm/IOCTL_CDROM_READ_TOC, k307_8e0f2b70-edd0-424e-abb4-a81ea9f382fe.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: Obsolete, beginning with Windows Vista.
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
-	IOCTL_CDROM_READ_TOC
product: Windows
targetos: Windows
req.typenames: WRITE_ROTATION, *PWRITE_ROTATION
---

# IOCTL_CDROM_READ_TOC IOCTL
Returns the table of contents of the media.  Obsolete, beginning with Windows Vista.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
Input buffer.

### Input Buffer Length
<i>
       Parameters.DeviceIoControl.OutputBufferLength</i> in the I/O stack location indicates the size, in bytes, of the buffer, which must be greater than or equal to  <b>sizeof</b>(CDROM_TOC).

### Output Buffer
The driver returns the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc.md">CDROM_TOC</a> data in the buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i>.

### Output Buffer Length
Length of a <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc.md">CDROM_TOC</a>.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL, STATUS_NO_MEDIA_IN_DEVICE, STATUS_DEVICE_NOT_READY, STATUS_IO_TIMEOUT, STATUS_IO_DEVICE_ERROR, STATUS_DEVICE_BUSY, or STATUS_VERIFY_REQUIRED.

## Remarks
Beginning with Windows Vista, CDROM class drivers do not use this IOCTL. Prior to Windows Vista, this IOCTL was used for audio playback on older CD-ROM drives that supported direct audio output in hardware.

Client applications should use the <i>Media Control Interface (MCI) API</i> rather than issuing this IOCTL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Obsolete, beginning with Windows Vista. Obsolete, beginning with Windows Vista. |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc.md">CDROM_TOC</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CDROM_READ_TOC control code%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>