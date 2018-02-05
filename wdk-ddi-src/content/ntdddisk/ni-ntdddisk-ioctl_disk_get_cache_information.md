---
UID : NI:ntdddisk.IOCTL_DISK_GET_CACHE_INFORMATION
title : IOCTL_DISK_GET_CACHE_INFORMATION
author : windows-driver-content
description : Returns disk cache configuration data.
old-location : storage\ioctl_disk_get_cache_information.htm
old-project : storage
ms.assetid : fc651954-2048-4358-91b0-4d99e38e9a67
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ioctl_disk_get_cache_information, IOCTL_DISK_GET_CACHE_INFORMATION control code [Storage Devices], IOCTL_DISK_GET_CACHE_INFORMATION, ntdddisk/IOCTL_DISK_GET_CACHE_INFORMATION, k307_1471eb7a-169f-4653-9bfe-01714d6299b7.xml
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

# IOCTL_DISK_GET_CACHE_INFORMATION IOCTL
Returns disk cache configuration data.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
The device driver returns the <a href="..\ntdddisk\ns-ntdddisk-_disk_cache_information.md">DISK_CACHE_INFORMATION</a> in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

### Output Buffer Length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer made available to the driver, which must be &gt;= <b>sizeof</b>(DISK_CACHE_INFORMATION). Otherwise, the driver returns with an error status of STATUS_BUFFER_TOO_SMALL.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to the size of the block of status information being returned, <b>sizeof</b>(DISK_CACHE_INFORMATION). The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_DEVICE_NOT_READY, STATUS_BUFFER_TOO_SMALL, STATUS_INSUFFICIENT_RESOURCES, STATUS_IO_DEVICE_ERROR, or STATUS_NOT_SUPPORTED.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntdddisk.h (include Ntdddisk.h) |

## See Also

<a href="..\ntdddisk\ns-ntdddisk-_disk_cache_information.md">DISK_CACHE_INFORMATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_DISK_GET_CACHE_INFORMATION control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>