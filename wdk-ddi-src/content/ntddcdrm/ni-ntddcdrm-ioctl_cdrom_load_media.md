---
UID: NI:ntddcdrm.IOCTL_CDROM_LOAD_MEDIA
title: IOCTL_CDROM_LOAD_MEDIA
author: windows-driver-content
description: Draws a protruding CDROM tray back into the drive.
old-location: storage\ioctl_cdrom_load_media.htm
old-project: storage
ms.assetid: 2add532c-fd98-41f9-93a4-d7d238bc88d0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_CDROM_LOAD_MEDIA, IOCTL_CDROM_LOAD_MEDIA control code [Storage Devices], k307_f623cca5-938f-483e-a133-e24c763ec189.xml, ntddcdrm/IOCTL_CDROM_LOAD_MEDIA, storage.ioctl_cdrom_load_media
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
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
-	ntddcdrm.h
api_name:
-	IOCTL_CDROM_LOAD_MEDIA
product: Windows
targetos: Windows
req.typenames: WRITE_ROTATION, *PWRITE_ROTATION
---

# IOCTL_CDROM_LOAD_MEDIA IOCTL
Draws a protruding CDROM tray back into the drive.

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
The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS if the operation is successful, or possibly to STATUS_INSUFFICIENT_RESOURCES if insufficient resources are available to complete the operation.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |