---
UID : NI:ntddstor.IOCTL_STORAGE_REINITIALIZE_MEDIA
title : IOCTL_STORAGE_REINITIALIZE_MEDIA
author : windows-driver-content
description : A driver can use the IOCTL_STORAGE_REINITIALIZE_MEDIA control code to reinitialize/erase a device.
old-location : storage\ioctl_storage_reinitialize_media.htm
old-project : storage
ms.assetid : 4ECF51C3-D098-49E2-A675-78066A15C221
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ioctl_storage_reinitialize_media, IOCTL_STORAGE_REINITIALIZE_MEDIA control code [Storage Devices], IOCTL_STORAGE_REINITIALIZE_MEDIA, ntddstor/IOCTL_STORAGE_REINITIALIZE_MEDIA
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ntddstor.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10, version 1607
req.target-min-winversvr : Windows Server 2016
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
req.typenames : "*PSTORAGE_ZONE_CONDITION, STORAGE_ZONE_CONDITION"
---

# IOCTL_STORAGE_REINITIALIZE_MEDIA IOCTL
A driver can use the <b> IOCTL_STORAGE_REINITIALIZE_MEDIA</b> control code to reinitialize/erase a device. The IOCTL offloads the erasure to the storage device; there is no guarantee as to the successful deletion or recoverability of the data of the storage device after the command completes.  This IOCTL is limited to data disks on devices in the desktop device family. In Windows Preinstallation Environment (WinPE), this IOCTL is supported for both boot and data disks.

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
The <b>Information</b> field is set to zero if the operation completes successfully; otherwise, it is set to a non-zero value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | ntddstor.h |
| **IRQL** |  |