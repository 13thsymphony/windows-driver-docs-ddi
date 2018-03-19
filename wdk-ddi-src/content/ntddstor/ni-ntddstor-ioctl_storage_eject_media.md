---
UID: NI:ntddstor.IOCTL_STORAGE_EJECT_MEDIA
title: IOCTL_STORAGE_EJECT_MEDIA
author: windows-driver-content
description: Causes the device to eject the media if the device supports ejection capabilities.
old-location: storage\ioctl_storage_eject_media.htm
old-project: storage
ms.assetid: 094edf6d-276b-4aae-9e60-52e181268e7d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_STORAGE_EJECT_MEDIA, IOCTL_STORAGE_EJECT_MEDIA control code [Storage Devices], k307_19063683-2dc1-4ce2-ac53-7754eee2562b.xml, ntddstor/IOCTL_STORAGE_EJECT_MEDIA, storage.ioctl_storage_eject_media
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
-	IOCTL_STORAGE_EJECT_MEDIA
product: Windows
targetos: Windows
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_EJECT_MEDIA IOCTL
Causes the device to eject the media if the device supports ejection capabilities.

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
The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_NO_MEDIA_IN_DEVICE or STATUS_INVALID_DEVICE_REQUEST.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddstor.h (include Ntddstor.h) |

## See Also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_ejection_control.md">IOCTL_STORAGE_EJECTION_CONTROL</a>