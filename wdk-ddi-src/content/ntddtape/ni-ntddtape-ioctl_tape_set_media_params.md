---
UID: NI:ntddtape.IOCTL_TAPE_SET_MEDIA_PARAMS
title: IOCTL_TAPE_SET_MEDIA_PARAMS
author: windows-driver-content
description: Resets the block size of the media in the drive.
old-location: storage\ioctl_tape_set_media_params.htm
old-project: storage
ms.assetid: c1411e72-84b4-4021-bed6-17308415be3a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_TAPE_SET_MEDIA_PARAMS, IOCTL_TAPE_SET_MEDIA_PARAMS control code [Storage Devices], k307_c549601d-5c5e-452b-8880-844820207215.xml, ntddtape/IOCTL_TAPE_SET_MEDIA_PARAMS, storage.ioctl_tape_set_media_params
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddtape.h
req.include-header: Ntddtape.h
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
-	Ntddtape.h
api_name:
-	IOCTL_TAPE_SET_MEDIA_PARAMS
product: Windows
targetos: Windows
req.typenames: TAPE_DRIVE_PROBLEM_TYPE
---

# IOCTL_TAPE_SET_MEDIA_PARAMS IOCTL
Resets the block size of the media in the drive.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="..\ntddtape\ns-ntddtape-_tape_set_media_parameters.md">TAPE_SET_MEDIA_PARAMETERS</a> structure containing the block size to be set.

### Input Buffer Length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(TAPE_SET_MEDIA_PARAMETERS).

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_IO_DEVICE_ERROR, STATUS_MEDIA_WRITE_PROTECTED, STATUS_DEVICE_DATA_ERROR, STATUS_NO_SUCH_DEVICE, STATUS_IO_TIMEOUT, STATUS_DEVICE_NOT_READY, STATUS_INFO_LENGTH_MISMATCH, STATUS_NO_MEDIA_IN_DEVICE, or STATUS_VERIFY_REQUIRED.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddtape.h (include Ntddtape.h) |

## See Also

<a href="..\ntddtape\ns-ntddtape-_tape_set_media_parameters.md">TAPE_SET_MEDIA_PARAMETERS</a>



<a href="..\minitape\ne-minitape-_tape_status.md">TAPE_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567953">TapeMiniSetMediaParameters</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_TAPE_SET_MEDIA_PARAMS control code%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>