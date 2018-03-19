---
UID: NI:ntddtape.IOCTL_TAPE_GET_STATUS
title: IOCTL_TAPE_GET_STATUS
author: windows-driver-content
description: Returns the current status of the drive in the Status field of the I/O status block.
old-location: storage\ioctl_tape_get_status.htm
old-project: storage
ms.assetid: d5e491b8-d40c-4f2c-9117-5c3cb71913f7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_TAPE_GET_STATUS, IOCTL_TAPE_GET_STATUS control code [Storage Devices], k307_8ab90364-adac-4937-9036-aa28ddeffb19.xml, ntddtape/IOCTL_TAPE_GET_STATUS, storage.ioctl_tape_get_status
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
-	IOCTL_TAPE_GET_STATUS
product: Windows
targetos: Windows
req.typenames: TAPE_DRIVE_PROBLEM_TYPE
---

# IOCTL_TAPE_GET_STATUS IOCTL
Returns the current status of the drive in the <b>Status</b> field of the I/O status block.

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
The <b>Information</b> field is set to zero. The <b>Status</b> field is set to one of the following NT status values: 

<ul>
<li>
STATUS_SUCCESS

</li>
<li>
STATUS_INSUFFICIENT_RESOURCES

</li>
<li>
STATUS_NOT_IMPLEMENTED

</li>
<li>
STATUS_INVALID_DEVICE_REQUEST

</li>
<li>
STATUS_INVALID_PARAMETER

</li>
<li>
STATUS_VERIFY_REQUIRED

</li>
<li>
STATUS_BUS_RESET

</li>
<li>
STATUS_SETMARK_DETECTED

</li>
<li>
STATUS_FILEMARK_DETECTED

</li>
<li>
STATUS_BEGINNING_OF_MEDIA

</li>
<li>
STATUS_END_OF_MEDIA

</li>
<li>
STATUS_BUFFER_OVERFLOW

</li>
<li>
STATUS_NO_DATA_DETECTED

</li>
<li>
STATUS_EOM_OVERFLOW

</li>
<li>
STATUS_NO_MEDIA

</li>
<li>
STATUS_IO_DEVICE_ERROR

</li>
<li>
STATUS_UNRECOGNIZED_MEDIA

</li>
<li>
STATUS_DEVICE_NOT_READY

</li>
<li>
STATUS_MEDIA_WRITE_PROTECTED

</li>
<li>
STATUS_DEVICE_DATA_ERROR

</li>
<li>
STATUS_NO_SUCH_DEVICE

</li>
<li>
STATUS_INVALID_BLOCK_LENGTH

</li>
<li>
STATUS_IO_TIMEOUT

</li>
<li>
STATUS_DEVICE_NOT_CONNECTED

</li>
<li>
STATUS_DATA_OVERRUN

</li>
<li>
STATUS_DEVICE_BUSY

</li>
<li>
STATUS_DEVICE_REQUIRES_CLEANING

</li>
<li>
STATUS_CLEANER_CARTRIDGE_INSTALLED

</li>
</ul>
Each of these NT status values correspond to a value in the <a href="..\minitape\ne-minitape-_tape_status.md">TAPE_STATUS</a> enumerator. For more information about the significance of these values and a mapping between the NT status values and the TAPE_STATUS values, see <a href="https://msdn.microsoft.com/de6edfc6-9b4b-4866-8fdb-1047b43163de">Processing Tape Device Control Requests</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddtape.h (include Ntddtape.h) |

## See Also

<a href="..\minitape\ne-minitape-_tape_status.md">TAPE_STATUS</a>