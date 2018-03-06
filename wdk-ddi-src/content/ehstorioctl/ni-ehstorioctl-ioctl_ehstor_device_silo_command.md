---
UID: NI:ehstorioctl.IOCTL_EHSTOR_DEVICE_SILO_COMMAND
title: IOCTL_EHSTOR_DEVICE_SILO_COMMAND
author: windows-driver-content
description: This IOCTL issues a silo command to the targeted silo on the device. Both input and output data are structured according to the definition of silo commands, as found in the IEEE 1667 specification document.
old-location: storage\ioctl_ehstor_device_silo_command.htm
old-project: storage
ms.assetid: 3258FA16-E1FE-4CBF-8C87-0C7A8B2A7EBF
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_EHSTOR_DEVICE_SILO_COMMAND, IOCTL_EHSTOR_DEVICE_SILO_COMMAND control code [Storage Devices], ehstorioctl/IOCTL_EHSTOR_DEVICE_SILO_COMMAND, storage.ioctl_ehstor_device_silo_command
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
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
-	EhStorIoctl.h
api_name:
-	IOCTL_EHSTOR_DEVICE_SILO_COMMAND
product: Windows
targetos: Windows
req.typenames: PDO_TYPE
---

# IOCTL_EHSTOR_DEVICE_SILO_COMMAND IOCTL
This IOCTL issues a silo command to the targeted silo on the device. Both input and output data are structured according to the definition of silo commands, as found in the IEEE 1667 specification document.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The input buffer at Irp-&gt;AssociatedIrp.SystemBuffer must contain a structure of type <a href="..\ehstorioctl\ns-ehstorioctl-tagsilo_command.md">SILO_COMMAND</a>.

### Input Buffer Length
The length of a <a href="..\ehstorioctl\ns-ehstorioctl-tagsilo_command.md">SILO_COMMAND</a> structure.

### Output Buffer
The output buffer contains the output data returned directly from the device response to this silo command. The structure of this output data is assumed to be shared knowledge between the client issuing this IOCTL and the device.

### Output Buffer Length
The length of the buffer.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
One of the following values may be returned in the Status field:


<dl>
<dd>
STATUS_SUCCESS - The silo command was successfully issued to the device.

</dd>
</dl>



<dl>
<dd>
STATUS_INVALID_BUFFER_SIZE - The input buffer length supplied is of incorrect size.

</dd>
</dl>



<dl>
<dd>
STATUS_BUFFER_TOO_SMALL - The output buffer length supplied is of insufficient size to hold the device response for this silo command.

</dd>
</dl>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ehstorioctl.h (include EhStorIoctl.h) |