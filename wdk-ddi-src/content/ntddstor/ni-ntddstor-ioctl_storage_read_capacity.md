---
UID: NI:ntddstor.IOCTL_STORAGE_READ_CAPACITY
title: IOCTL_STORAGE_READ_CAPACITY
author: windows-driver-content
description: The IOCTL_STORAGE_READ_CAPACITY request returns the read capacity information for the target storage device.
old-location: storage\ioctl_storage_read_capacity.htm
old-project: storage
ms.assetid: FC4CFD33-5632-400A-90E5-583C6D6DFFD9
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_storage_read_capacity, IOCTL_STORAGE_READ_CAPACITY control code [Storage Devices], IOCTL_STORAGE_READ_CAPACITY, ntddstor/IOCTL_STORAGE_READ_CAPACITY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
-	Ntddstor.h
apiname:
-	IOCTL_STORAGE_READ_CAPACITY
product: Windows
targetos: Windows
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_READ_CAPACITY IOCTL
The <b>IOCTL_STORAGE_READ_CAPACITY</b> request returns the read capacity information for the target storage device.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
The buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i> contains a <a href="..\ntddstor\ns-ntddstor-_storage_read_capacity.md">STORAGE_READ_CAPACITY</a> structure.

### Output Buffer Length
<i>Parameters.DeviceIoControl.OutputBufferLength</i> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b>(STORAGE_READ_CAPACITY).

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Status</b> field can be set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_BUFFER_TOO_SMALL, STATUS_BUFFER_OVERFLOW, or some other error status.

## Remarks
A <b>IOCTL_STORAGE_READ_CAPACITY</b> request returns the disk capacity information retrieved during disk initialization. The capacity information is obtained by the system with the SCSI READ CAPACITY command.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Header** | ntddstor.h (include Ntddstor.h) |

## See Also

<a href="..\ntddstor\ns-ntddstor-_storage_read_capacity.md">STORAGE_READ_CAPACITY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_READ_CAPACITY control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>