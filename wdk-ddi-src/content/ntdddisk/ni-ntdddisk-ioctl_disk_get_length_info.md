---
UID: NI:ntdddisk.IOCTL_DISK_GET_LENGTH_INFO
title: IOCTL_DISK_GET_LENGTH_INFO
author: windows-driver-content
description: Returns the length, in bytes, of the disk, partition, or volume associated with the device object that is the target of the request.
old-location: storage\ioctl_disk_get_length_info.htm
old-project: storage
ms.assetid: 62d31b13-bc4a-4b2f-82be-551a61cae218
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_DISK_GET_LENGTH_INFO, IOCTL_DISK_GET_LENGTH_INFO control code [Storage Devices], k307_50fea771-4937-481d-9a1b-f4d69bb939bb.xml, ntdddisk/IOCTL_DISK_GET_LENGTH_INFO, storage.ioctl_disk_get_length_info
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows XP and later operating systems.
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
-	IOCTL_DISK_GET_LENGTH_INFO
product: Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_GET_LENGTH_INFO IOCTL
Returns the length, in bytes, of the disk, partition, or volume associated with the device object that is the target of the request.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
The driver returns the <a href="..\ntdddisk\ns-ntdddisk-_get_length_information.md">GET_LENGTH_INFORMATION</a> data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

### Output Buffer Length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(GET_LENGTH_INFORMATION).

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to the size, in bytes, of the returned data. The <b>Status</b> field can be set to STATUS_SUCCESS, or to STATUS_BUFFER_TOO_SMALL if the buffer supplied by the caller is inadequate.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in Windows XP and later operating systems. Supported in Windows XP and later operating systems. |
| **Header** | ntdddisk.h (include Ntdddisk.h) |

## See Also

<a href="..\ntdddisk\ns-ntdddisk-_get_length_information.md">GET_LENGTH_INFORMATION</a>