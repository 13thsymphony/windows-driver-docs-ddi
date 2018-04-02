---
UID: NI:ntddstor.IOCTL_STORAGE_PROTOCOL_COMMAND
title: IOCTL_STORAGE_PROTOCOL_COMMAND
author: windows-driver-content
description: A driver can use IOCTL_STORAGE_PROTOCOL_COMMAND to pass vendor-specific commands to a storage device.
old-location: storage\ioctl_storage_protocol_command.htm
old-project: storage
ms.assetid: 1AA59350-2475-4BF7-B447-42FDDB311882
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_STORAGE_PROTOCOL_COMMAND, IOCTL_STORAGE_PROTOCOL_COMMAND control code [Storage Devices], ntddstor/IOCTL_STORAGE_PROTOCOL_COMMAND, storage.ioctl_storage_protocol_command
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	ntddstor.h
api_name:
-	IOCTL_STORAGE_PROTOCOL_COMMAND
product: Windows
targetos: Windows
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_PROTOCOL_COMMAND IOCTL
A driver can use <b>IOCTL_STORAGE_PROTOCOL_COMMAND</b> to pass vendor-specific commands to a storage device.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
The driver returns the results of the vendor-specific command to the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. Cast the structure returned to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn931814">STORAGE_PROTOCOL_COMMAND</a> and check its <b>ReturnStatus</b> field to determine the status of the command request.

### Output Buffer Length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(<a href="https://msdn.microsoft.com/library/windows/hardware/dn931814">STORAGE_PROTOCOL_COMMAND</a>).

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to <b>STATUS_SUCCESS</b>, or possibly to <b>STATUS_INSUFFICIENT_RESOURCES</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | ntddstor.h (include Ntddstor.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn931814">STORAGE_PROTOCOL_COMMAND</a>