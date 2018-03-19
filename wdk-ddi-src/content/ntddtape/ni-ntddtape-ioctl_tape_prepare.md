---
UID: NI:ntddtape.IOCTL_TAPE_PREPARE
title: IOCTL_TAPE_PREPARE
author: windows-driver-content
description: Loads or unloads the tape, resets tape tension, locks or unlocks the ejection mechanism, or formats the tape.
old-location: storage\ioctl_tape_prepare.htm
old-project: storage
ms.assetid: 0e016f3a-4f3a-4256-bb7b-10a5f955b930
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_TAPE_PREPARE, IOCTL_TAPE_PREPARE control code [Storage Devices], k307_a564f3c9-909a-437c-973c-0e6c25fad061.xml, ntddtape/IOCTL_TAPE_PREPARE, storage.ioctl_tape_prepare
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddtape.h
req.include-header: Ntddtape.h
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
-	Ntddtape.h
api_name:
-	IOCTL_TAPE_PREPARE
product: Windows
targetos: Windows
req.typenames: TAPE_DRIVE_PROBLEM_TYPE
---

# IOCTL_TAPE_PREPARE IOCTL
Loads or unloads the tape, resets tape tension, locks or unlocks the ejection mechanism, or formats the tape.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="..\ntddtape\ns-ntddtape-_tape_prepare.md">TAPE_PREPARE</a> structure that indicates the type of operation.

If the <b>Immediate</b> member is <b>TRUE</b>, the operation should be asynchronous.

### Input Buffer Length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(TAPE_PREPARE).

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_NO_SUCH_DEVICE, STATUS_IO_TIMEOUT, STATUS_IO_DEVICE_ERROR, STATUS_INSUFFICIENT_RESOURCES, STATUS_DEVICE_NOT_CONNECTED, STATUS_MEDIA_WRITE_PROTECTED, STATUS_NO_MEDIA_IN_DEVICE, or STATUS_VERIFY_REQUIRED.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddtape.h (include Ntddtape.h) |

## See Also

<a href="..\minitape\ne-minitape-_tape_status.md">TAPE_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567950">TapeMiniPrepare</a>



<a href="..\ntddtape\ns-ntddtape-_tape_prepare.md">TAPE_PREPARE</a>