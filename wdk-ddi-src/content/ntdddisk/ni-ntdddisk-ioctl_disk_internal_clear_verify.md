---
UID: NI:ntdddisk.IOCTL_DISK_INTERNAL_CLEAR_VERIFY
title: IOCTL_DISK_INTERNAL_CLEAR_VERIFY
author: windows-driver-content
description: Allows a driver to clear the verify bit on a disk device object, if the mode of the caller is kernel mode.
old-location: storage\ioctl_disk_internal_clear_verify.htm
old-project: storage
ms.assetid: 72d3b112-a5d2-4b2d-8102-bd3dfba31500
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_DISK_INTERNAL_CLEAR_VERIFY, IOCTL_DISK_INTERNAL_CLEAR_VERIFY control code [Storage Devices], k307_bc80d35d-1d7f-4eb1-a2c7-da87c58a4f62.xml, ntdddisk/IOCTL_DISK_INTERNAL_CLEAR_VERIFY, storage.ioctl_disk_internal_clear_verify
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
-	Ntdddisk.h
api_name:
-	IOCTL_DISK_INTERNAL_CLEAR_VERIFY
product: Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_INTERNAL_CLEAR_VERIFY IOCTL
Allows a driver to clear the verify bit on a disk device object, if the mode of the caller is kernel mode.

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
The <b>Status</b> field is set to STATUS_SUCCESS. If the mode of the requester is not kernel mode, the requested operation is not performed, but STATUS_SUCCESS is still returned.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntdddisk.h (include Ntdddisk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560380">IOCTL_DISK_INTERNAL_SET_VERIFY</a>