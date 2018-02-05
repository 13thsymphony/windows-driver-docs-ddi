---
UID : NI:ntddstor.IOCTL_STORAGE_FIND_NEW_DEVICES
title : IOCTL_STORAGE_FIND_NEW_DEVICES
author : windows-driver-content
description : Determines whether another device that the driver supports has been connected to the I/O bus, either since the system was booted or since the driver last processed this request.
old-location : storage\ioctl_storage_find_new_devices.htm
old-project : storage
ms.assetid : 359169a3-602d-4910-badf-c777c1a804e7
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ioctl_storage_find_new_devices, IOCTL_STORAGE_FIND_NEW_DEVICES control code [Storage Devices], IOCTL_STORAGE_FIND_NEW_DEVICES, ntddstor/IOCTL_STORAGE_FIND_NEW_DEVICES, k307_2bd9c727-e25a-4c21-9173-af7bc2c830c6.xml
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

# IOCTL_STORAGE_FIND_NEW_DEVICES IOCTL
Determines whether another device that the driver supports has been connected to the I/O bus, either since the system was booted or since the driver last processed this request. 

This IOCTL is obsolete in the Plug and Play environment. Plug and Play class drivers handle this request by calling <a href="..\wdm\nf-wdm-ioinvalidatedevicerelations.md">IoInvalidateDeviceRelations</a> with the device relations type <b>BusRelations</b>. If a new device is found, the class driver's <i>AddDevice</i> routine will be called. 

Legacy class drivers can continue to handle this IOCTL without modifications. If a new device is found, the driver sets up any necessary system objects and resources to handle I/O requests for its new device. It also initializes the device on receipt of this request dynamically, that is, without requiring the machine to be rebooted. Such a driver is assumed to support devices connected on a dynamically configurable I/O bus.

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
The <b>Information</b> field is set to zero. The <b>Status</b> field can be set to STATUS_SUCCESS or to any other value returned by a Plug and Play driver's <b>IoInvalidateDeviceRelations</b> call or a legacy driver's (re)initialization code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddstor.h (include Ntddstor.h) |