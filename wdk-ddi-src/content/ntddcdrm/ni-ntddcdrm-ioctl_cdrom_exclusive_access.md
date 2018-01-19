---
UID : NI:ntddcdrm.IOCTL_CDROM_EXCLUSIVE_ACCESS
title : IOCTL_CDROM_EXCLUSIVE_ACCESS
author : windows-driver-content
description : The IOCTL_CDROM_EXCLUSIVE_ACCESS request instructs the CD-ROM class driver to:Report the access state of a CD-ROM device.
old-location : storage\ioctl_cdrom_exclusive_access.htm
old-project : storage
ms.assetid : 449936d8-9257-4044-a38f-e68d8e8d5c68
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _WRITE_ROTATION, WRITE_ROTATION, *PWRITE_ROTATION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ntddcdrm.h
req.include-header : Ntddcdrm.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IOCTL_CDROM_EXCLUSIVE_ACCESS
req.alt-loc : Ntddcdrm.h
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

# IOCTL_CDROM_EXCLUSIVE_ACCESS IOCTL
The IOCTL_CDROM_EXCLUSIVE_ACCESS request instructs the CD-ROM class driver to:<ul>
<li>
Report the access state of a CD-ROM device. 

</li>
<li>
Lock a CD-ROM device for exclusive access. 

</li>
<li>
Unlock a CD-ROM device for exclusive access. 

</li>
</ul>
A valid FileObject handle must exist in order for this IOCTL to succeed. The FileObject handle protects the system from unexpected application termination or accidental acquisition of an exclusive access lock without subsequent release of the exclusive access lock. A valid FileObject handle is necessary because when an application closes, the CD-ROM class driver will receive CLEANUP and CLOSE I/O Request Packets (IRPs), which it can use to automatically release an exclusive access lock obtained by that handle. This simple method protects against the majority of accidental releases of exclusive access. Any methods used to avoid this functionality may reduce the safety and effectiveness of the exclusive access locking method.



Report the access state of a CD-ROM device. 

Lock a CD-ROM device for exclusive access. 

Unlock a CD-ROM device for exclusive access. 

A valid FileObject handle must exist in order for this IOCTL to succeed. The FileObject handle protects the system from unexpected application termination or accidental acquisition of an exclusive access lock without subsequent release of the exclusive access lock. A valid FileObject handle is necessary because when an application closes, the CD-ROM class driver will receive CLEANUP and CLOSE I/O Request Packets (IRPs), which it can use to automatically release an exclusive access lock obtained by that handle. This simple method protects against the majority of accidental releases of exclusive access. Any methods used to avoid this functionality may reduce the safety and effectiveness of the exclusive access locking method.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
Depending on the operation that the caller requests, the caller must provide one of the following structures as input at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>:


<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_exclusive_access.md">CDROM_EXCLUSIVE_ACCESS</a> (to report the access state of a CD-ROM device)


<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_exclusive_lock.md">CDROM_EXCLUSIVE_LOCK</a> (to lock a CD-ROM device for exclusive access)


<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_exclusive_access.md">CDROM_EXCLUSIVE_ACCESS</a> (to unlock a CD-ROM device that the application locked for exclusive access)

### Input Buffer Length
The <b>Parameters.DeviceIoControl.InputBufferLength</b> member in the <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structure indicates the size, in bytes, of the user-allocated input buffer.

### Output Buffer
If the caller requests the exclusive access state of the CD-ROM device (<b>RequestType</b> = <b>ExclusiveAccessQueryState</b>), the CD-ROM class driver returns a <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_exclusive_lock_state.md">CDROM_EXCLUSIVE_LOCK_STATE</a>-type structure in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer </b>whose <b>LockState</b> member indicates the access state of the device.

### Output Buffer Length
The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member in the I/O stack location (IO_STACK_LOCATION) indicates the size, in bytes, of the output buffer.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
I/O Status block
The <b>Information</b> field is set to the number of bytes that are returned. The <b>Status</b> field is set to STATUS_SUCCESS if the request succeeds. 

If the request fails, the <b>Status</b> field might be set to one of the following error messages:



The input buffer was too small. 

The output buffer was too small for a <b>ExclusiveAccessQueryState</b> request. 

The CD-ROM class driver returns this status code when one of the following two errors occurs:

The <b>RequestType</b> that was specified is not a valid member of <a href="..\ntddcdrm\ne-ntddcdrm-_exclusive_access_request_type.md">EXCLUSIVE_ACCESS_REQUEST_TYPE</a>.  

The caller name string in the <b>CallerName</b> member of <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_exclusive_lock.md">CDROM_EXCLUSIVE_LOCK</a> violates the naming convention. <b>CallerName</b> must be a <b>NULL</b>-terminated string that contains the following characters: alphanumerics (A - Z, a - z, 0 - 9), spaces, periods, commas, colons (:), semi-colons (;), hyphens (-), and underscores (_). The length of the string must be less than CDROM_EXCLUSIVE_CALLER_LENGTH bytes, including the <b>NULL</b> at the end of the string. 

The CD-ROM class driver returns this status code when one of the following two errors occurs:

The caller made the request at an IRQL level other than PASSIVE_LEVEL.  

The caller sent a request with <b>RequestType</b> = <b>ExclusiveAccessUnlockDevice</b> to unlock a device that is not in exclusive mode. 

The CD-ROM class driver returns this status code when one of the following two errors occurs:

The file object that is required to keep track of the request was not available. The CD-ROM class driver did not receive a request to create a file object from this caller.  

The caller sent a request with <b>RequestType</b> = <b>ExclusiveAccessUnlockDevice</b> to unlock a device, even though the caller does not have exclusive access to the device. 

The caller attempted to lock a device while the file system driver was mounted on this device, without specifying that the class driver should suspend the check for a mounted file system driver. To suspend the check for a mounted file system driver, the caller must set the <b>Flags</b> member of <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_exclusive_access.md">CDROM_EXCLUSIVE_ACCESS</a> to 1. 

The device is already locked for exclusive access.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |
| **IRQL** |  |

    ## See Also

        <dl>
<dt>
<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_exclusive_access.md">CDROM_EXCLUSIVE_ACCESS</a>
</dt>
<dt>
<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_exclusive_lock.md">CDROM_EXCLUSIVE_LOCK</a>
</dt>
<dt>
<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_exclusive_lock_state.md">CDROM_EXCLUSIVE_LOCK_STATE</a>
</dt>
<dt>
<a href="..\ntddcdrm\ne-ntddcdrm-_exclusive_access_request_type.md">EXCLUSIVE_ACCESS_REQUEST_TYPE</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CDROM_EXCLUSIVE_ACCESS control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>