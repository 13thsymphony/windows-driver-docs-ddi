---
UID : NI:ntdddisk.IOCTL_DISK_PERFORMANCE_OFF
title : IOCTL_DISK_PERFORMANCE_OFF
author : windows-driver-content
description : Disables the counters that were enabled by previous calls to IOCTL_DISK_PERFORMANCE. This request is available in Windows XP and later operating systems. Caller must be running at IRQL = PASSIVE_LEVEL.
old-location : storage\ioctl_disk_performance_off.htm
old-project : storage
ms.assetid : 9a56ac86-2d39-4367-8e64-b6f6bc0da0ea
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ioctl_disk_performance_off, IOCTL_DISK_PERFORMANCE_OFF control code [Storage Devices], IOCTL_DISK_PERFORMANCE_OFF, ntdddisk/IOCTL_DISK_PERFORMANCE_OFF, k307_af1f6a33-e2e5-4ba0-96ad-f1d84c30ef76.xml
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
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DETECTION_TYPE
---

# IOCTL_DISK_PERFORMANCE_OFF IOCTL
Disables the counters that were enabled by previous calls to <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_performance.md">IOCTL_DISK_PERFORMANCE</a>. This request is available in Windows XP and later operating systems. Caller must be running at IRQL = PASSIVE_LEVEL.

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
The <b>Information</b> member is set to zero. The <b>Status</b> member is set to STATUS_SUCCESS if the operation was successful. Otherwise, the <b>Status</b> member is set to the appropriate error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | ntdddisk.h (include Ntdddisk.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_performance.md">IOCTL_DISK_PERFORMANCE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_DISK_PERFORMANCE_OFF control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>