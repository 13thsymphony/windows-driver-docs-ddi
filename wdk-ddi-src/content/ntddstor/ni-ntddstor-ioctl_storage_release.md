---
UID : NI:ntddstor.IOCTL_STORAGE_RELEASE
title : IOCTL_STORAGE_RELEASE
author : windows-driver-content
description : Releases a device previously reserved for the exclusive use of the caller on a bus that supports multiple initiators and the concept of reserving a device, such as a SCSI bus.
old-location : storage\ioctl_storage_release.htm
old-project : storage
ms.assetid : ca43da4e-6e0e-4689-83db-3f5ee5e560b2
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ioctl_storage_release, IOCTL_STORAGE_RELEASE control code [Storage Devices], IOCTL_STORAGE_RELEASE, ntddstor/IOCTL_STORAGE_RELEASE, k307_8097610b-98ad-4bb2-9f16-2caca8bf7f0d.xml
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

# IOCTL_STORAGE_RELEASE IOCTL
Releases a device previously reserved for the exclusive use of the caller on a bus that supports multiple initiators and the concept of reserving a device, such as a SCSI bus.

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
The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddstor.h (include Ntddstor.h) |