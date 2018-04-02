---
UID: NI:ntddstor.IOCTL_STORAGE_RESET_BUS
title: IOCTL_STORAGE_RESET_BUS
author: windows-driver-content
description: Resets an I/O bus and, indirectly, each device on the bus.
old-location: storage\ioctl_storage_reset_bus.htm
old-project: storage
ms.assetid: 26c9d499-2d53-48b8-8704-3ec7b15e15d8
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_STORAGE_RESET_BUS, IOCTL_STORAGE_RESET_BUS control code [Storage Devices], k307_8a5629b9-44e4-4ed7-a481-a5b9efbeb083.xml, ntddstor/IOCTL_STORAGE_RESET_BUS, storage.ioctl_storage_reset_bus
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
-	IOCTL_STORAGE_RESET_BUS
product: Windows
targetos: Windows
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_RESET_BUS IOCTL
Resets an I/O bus and, indirectly, each device on the bus. Resetting the bus clears all device reservations and transfer speed settings, which must then be renegotiated, making it a time-consuming operation that should be used very rarely. The caller requires only read access to issue a bus reset. 

The <b>SrbStatus</b> flag of pending SRBs is set to SRB_STATUS_BUS_RESET.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566354">STORAGE_BUS_RESET_REQUEST</a> structure that specifies the path ID of the bus to reset.

### Input Buffer Length
The length of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566354">STORAGE_BUS_RESET_REQUEST</a> structure.

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES, STATUS_NOT_IMPLEMENTED, or STATUS_INVALID_DEVICE_REQUEST.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddstor.h (include Ntddstor.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566354">STORAGE_BUS_RESET_REQUEST</a>