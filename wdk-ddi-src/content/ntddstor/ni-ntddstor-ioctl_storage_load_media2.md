---
UID: NI:ntddstor.IOCTL_STORAGE_LOAD_MEDIA2
title: IOCTL_STORAGE_LOAD_MEDIA2
author: windows-driver-content
description: Causes media to be loaded in a device that the caller has opened with FILE_READ_ATTRIBUTES.
old-location: storage\ioctl_storage_load_media2.htm
old-project: storage
ms.assetid: ba458d46-9b5f-4ee3-80fa-59277e97fb4a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_STORAGE_LOAD_MEDIA2, IOCTL_STORAGE_LOAD_MEDIA2 control code [Storage Devices], k307_3952f49a-8ca1-42eb-afd0-cb0e6eef66fc.xml, ntddstor/IOCTL_STORAGE_LOAD_MEDIA2, storage.ioctl_storage_load_media2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
-	Ntddstor.h
api_name:
-	IOCTL_STORAGE_LOAD_MEDIA2
product: Windows
targetos: Windows
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_LOAD_MEDIA2 IOCTL
Causes media to be loaded in a device that the caller has opened with FILE_READ_ATTRIBUTES. Because no file system is mounted when a device is opened in this way, this request can be processed much more quickly than an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560567">IOCTL_STORAGE_LOAD_MEDIA</a> request.

Input, output, and I/O status block values for IOCTL_STORAGE_LOAD_MEDIA2 are identical to those for IOCTL_STORAGE_LOAD_MEDIA.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560567">IOCTL_STORAGE_LOAD_MEDIA</a>