---
UID : NI:ntifs.IOCTL_VOLSNAP_FLUSH_AND_HOLD_WRITES
title : IOCTL_VOLSNAP_FLUSH_AND_HOLD_WRITES
author : windows-driver-content
description : The IOCTL_VOLSNAP_FLUSH_AND_HOLD_WRITES control code is sent to force a flush of a file system before a volume shadow copy occurs.
old-location : ifsk\ioctl_volsnap_flush_and_hold_writes.htm
old-project : ifsk
ms.assetid : c9189ca4-8b0e-470b-b027-f629ed243534
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ifsk.ioctl_volsnap_flush_and_hold_writes, IOCTL_VOLSNAP_FLUSH_AND_HOLD_WRITES control code [Installable File System Drivers], IOCTL_VOLSNAP_FLUSH_AND_HOLD_WRITES, ntifs/IOCTL_VOLSNAP_FLUSH_AND_HOLD_WRITES, ioctl_ref_f21aed38-5d6d-4b8c-ac8a-6cd1738a3de7.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ntifs.h
req.include-header : Ntifs.h, Fltkernel.h
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
req.typenames : TOKEN_TYPE
---

# IOCTL_VOLSNAP_FLUSH_AND_HOLD_WRITES IOCTL
The <b>IOCTL_VOLSNAP_FLUSH_AND_HOLD_WRITES</b> control code is sent to force a flush of a file system before a volume shadow copy occurs. This IOCTL is issued as an IRP_MJ_DEVICE_CONTROL request that is sent only to the volume device object of a local file system and to file system filter drivers that may have attached to that volume. This IOCTL is most commonly sent by the Volume Shadow Copy Service, but it can also be issued by other user-mode applications or processes. It is also possible under special circumstances for this IOCTL to be sent by the Volume Shadow Copy Driver (volsnap.sys) during a hibernation request or before a crash dump. This IOCTL is sent to file system filter drivers, file system drivers, and other device drivers (storage filter drivers and storage drivers, for example) located below the file systems. 

When a file system such as NTFS receives IOCTL_VOLSNAP_FLUSH_AND_HOLD_WRITES, the file system should flush the volume to disk, forcing the disk structures of the file system into a consistent and up-to-date state. The file system should lock the file system in a read-only mountable state, blocking any new file system changes to prevent any cached disk pages from becoming dirty. Once the file system has put the file system in such a state, it must pass the IRP with the IOCTL_VOLSNAP_FLUSH_AND_HOLD_WRITES IOCTL down the stack to the next driver while continuing to keep the file system in such a read-only mountable state until the drivers below complete the IRP. When the IRP completes or is canceled, the file system then re-enables I/O on the volume and returns.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<b>IrpSp-&gt;Parameters.DeviceIoControl.IoControlCode</b> is set to IOCTL_VOLSNAP_FLUSH_AND_HOLD_WRITES.

### Input Buffer Length
<text></text>

### Output Buffer
None

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Status</b> member is set to STATUS_SUCCESS on success or an appropriate NTSTATUS value such as one of the following:

## Remarks
A shadow copy of a volume is a point-in-time copy of that volume. The shadow copy is primarily used by a backup application so that it may backup files in a consistent manner, even though files may really be changing during the time to complete the backup operation. A shadow copy can also be used to prepare a volume for a hibernation resulting from a PNP request and for crash dumps. 

Windows XP and later versions of the operating system include a framework for orchestrating the timing for a shadow copy, as well as a storage filter driver (not a file system filter driver) that uses a copy-on-write technique in order to create a shadow copy. The Volume Shadow Copy Service (VSS) orchestrates the shadow copy. The Volume Shadow Copy Driver, volsnap.sys, is a storage filter driver that loads on top of the storage stack below file systems.

One important snapshot-related IOCTL that affects file systems is IOCTL_VOLSNAP_FLUSH_AND_HOLD_WRITES. This IOCTL is actually intended for interpretation by file systems, even though it is an IOCTL. This is because all file systems should pass the IOCTL down to a lower-level driver that is waiting to process the IOCTL after the file system. 

IOCTL_VOLSNAP_FLUSH_AND_HOLD_WRITES is sent only to the volume device object of a local file system and to file system filter drivers that may have attached to that volume. The storage device object that is linked to the volume through the <b>RealDevice</b> member of the Volume Parameter Block (VPB) structure will always have one of the following device types: 

FILE_DEVICE_DISK

FILE_DEVICE_VIRTUAL_DISK

This IOCTL is not sent to remote file systems. 

When a local file system receives IOCTL_VOLSNAP_FLUSH_AND_HOLD_WRITES, the driver should create a consistent image of the file system metadata. The driver should not have any pages that are inconsistent with each other. The driver must flush any portion of its metadata and mapped cache buffers that it has not flushed to disk and hold writes until the IOCTL has been completed by lower-level drivers.

For minifilter file system drivers, the filter manager receives this IOCTL and issues a callback to the minifilter driver if the driver has registered to receive this IRP. When a minifilter driver or a legacy file system filter driver receives this IOCTL, the driver must flush any portion of its metadata that it has not flushed to disk. If the filter driver is using mapped cache buffers to write its metadata, then the file system will take care of all the flushing. The filter driver just needs to ensure that it not write to any of its mapped cache buffers while the file system is trying to flush changes out to disk. A legacy file system filter driver needs to pass the IRP down to the next driver in the stack. 

A driver may choose to flush data while holding this IRP containing the IOCTL_VOLSNAP_FLUSH_AND_HOLD_WRITES IOCTL before passing it to lower-level drivers. Any data flushed to the disk while holding this IOCTL before sending the IRP to the next lower-level driver will be data available on the resulting shadow copy. 

If this is a read-only volume, then there is normally nothing that a file system or file system filter driver needs to do when receiving this IOCTL except send it to the next lower-level driver.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntifs.h (include Ntifs.h, Fltkernel.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IOCTL_VOLSNAP_FLUSH_AND_HOLD_WRITES control code%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>