---
UID : NI:ntddcdrm.IOCTL_CDROM_CHECK_VERIFY
title : IOCTL_CDROM_CHECK_VERIFY
author : windows-driver-content
description : In Microsoft Windows 2000 and later operating systems, this IOCTL is replaced by IOCTL_STORAGE_CHECK_VERIFY. The only difference between the two IOCTLs is the base value.
old-location : storage\ioctl_cdrom_check_verify.htm
old-project : storage
ms.assetid : ad2a5f3d-a796-4579-aa23-91b99baa1186
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ioctl_cdrom_check_verify, IOCTL_CDROM_CHECK_VERIFY control code [Storage Devices], IOCTL_CDROM_CHECK_VERIFY, ntddcdrm/IOCTL_CDROM_CHECK_VERIFY, k307_ecbed4e9-b4e2-4b49-90e4-652011983e48.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ntddcdrm.h
req.include-header : TBD
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
req.typenames : WRITE_ROTATION, *PWRITE_ROTATION
---

# IOCTL_CDROM_CHECK_VERIFY IOCTL
In Microsoft Windows 2000 and later operating systems, this IOCTL is replaced by <a href="..\ntddstor\ni-ntddstor-ioctl_storage_check_verify.md">IOCTL_STORAGE_CHECK_VERIFY</a>. The only difference between the two IOCTLs is the base value.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<text></text>

### Input Buffer Length
<text></text>

### Output Buffer
<text></text>

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [XREF-LINK:NTSTATUS Values].


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdrm.h (include TBD) |