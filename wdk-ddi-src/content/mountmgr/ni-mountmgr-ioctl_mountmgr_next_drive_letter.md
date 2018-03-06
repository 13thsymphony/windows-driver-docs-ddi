---
UID: NI:mountmgr.IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER
title: IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER
author: windows-driver-content
description: This IOCTL checks to see if the given volume has a drive letter.
old-location: storage\ioctl_mountmgr_next_drive_letter.htm
old-project: storage
ms.assetid: 7e3c5718-180c-435d-89ea-30a5cac325b2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER, IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER control code [Storage Devices], k307_c77572b5-04ff-453d-91a4-9f58c65930e0.xml, mountmgr/IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER, storage.ioctl_mountmgr_next_drive_letter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: mountmgr.h
req.include-header: Mountmgr.h
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
-	Mountmgr.h
api_name:
-	IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER
product: Windows
targetos: Windows
req.typenames: MOUNTDEV_UNIQUE_ID, *PMOUNTDEV_UNIQUE_ID
---

# IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER IOCTL
This IOCTL checks to see if the given volume has a drive letter. If it already has a drive letter, or if the volume has a special mount manager database entry indicating that it does not require a drive letter, this routine returns the current drive letter (if there is one) and does nothing. If the given volume does not have a drive letter and does not have a special mount manager database entry indicating that it does not require a drive letter, the next available drive letter is assigned to the volume. If the volume's nonpersistent device name begins with "\Device\Floppy", the mount manager will check for available drive letters starting with the letter "A." If the volume name begins with "\Device\CdRom" the mount manager will check for available drive letters starting with drive letter "D." In all other cases, the mount manager starts with drive letter "C."

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The mount manager client initializes the <a href="..\mountmgr\ns-mountmgr-_mountmgr_drive_letter_target.md">MOUNTMGR_DRIVE_LETTER_TARGET</a> structure, defined in <i>Mountmgr.h</i>, at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. The client must insert the name of the target volume at the address pointed to by the <i>DeviceName[]</i> member of this structure. The target volume name is the name of the nonpersistent device object associated with the volume (for example, "\Device\HarddiskVolume1").

### Input Buffer Length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(MOUNTMGR_DRIVE_LETTER_TARGET).

### Output Buffer
The mount manager inserts either the current drive letter or the newly assigned drive letter (see previous discussion) in the <a href="..\mountmgr\ns-mountmgr-_mountmgr_drive_letter_information.md">MOUNTMGR_DRIVE_LETTER_INFORMATION</a> structure, defined in <i>Mountmgr.h</i>, at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

### Output Buffer Length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer, which must be greater than or equal to <b>sizeof</b>(MOUNTMGR_DRIVE_LETTER_INFORMATION).

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the operation is successful , the <b>Status</b> field is set to STATUS_SUCCESS.

If <b>InputBufferLength</b> is less than <b>sizeof</b>(MOUNTMGR_DRIVE_LETTER_TARGET) or if <b>OutputBufferLength</b> is less than <b>sizeof</b>(MOUNTMGR_DRIVE_LETTER_INFORMATION), the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | mountmgr.h (include Mountmgr.h) |

## See Also

<a href="..\mountmgr\ns-mountmgr-_mountmgr_drive_letter_target.md">MOUNTMGR_DRIVE_LETTER_TARGET</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER control code%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>