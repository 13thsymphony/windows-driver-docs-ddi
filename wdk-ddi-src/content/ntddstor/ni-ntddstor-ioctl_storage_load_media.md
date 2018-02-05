---
UID : NI:ntddstor.IOCTL_STORAGE_LOAD_MEDIA
title : IOCTL_STORAGE_LOAD_MEDIA
author : windows-driver-content
description : Causes media to be loaded in a device that the caller has opened for read or write access.
old-location : storage\ioctl_storage_load_media.htm
old-project : storage
ms.assetid : 137ebbec-53f7-4bf6-b43b-2c736d66eb97
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ioctl_storage_load_media, IOCTL_STORAGE_LOAD_MEDIA control code [Storage Devices], IOCTL_STORAGE_LOAD_MEDIA, ntddstor/IOCTL_STORAGE_LOAD_MEDIA, k307_730c4c03-9d36-406b-8965-270aa539d0ca.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ntddstor.h
req.include-header : Ntddstor.h
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
req.typenames : STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_LOAD_MEDIA IOCTL
Causes media to be loaded in a device that the caller has opened for read or write access. If read or write access to the device is not necessary, the caller can improve performance by opening the device with FILE_READ_ATTRIBUTES and issuing an <a href="..\ntddstor\ni-ntddstor-ioctl_storage_load_media2.md">IOCTL_STORAGE_LOAD_MEDIA2</a> request instead.

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
The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_NO_MEDIA_IN_DEVICE, STATUS_BUFFER_TOO_SMALL, or STATUS_DEVICE_NOT_CONNECTED.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddstor.h (include Ntddstor.h) |

## See Also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_load_media2.md">IOCTL_STORAGE_LOAD_MEDIA2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_LOAD_MEDIA control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>