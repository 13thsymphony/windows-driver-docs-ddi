---
UID: NI:ntddtape.IOCTL_TAPE_ERASE
title: IOCTL_TAPE_ERASE
author: windows-driver-content
description: Erases the current tape partition, either as a TAPE_ERASE_LONG (in other words, a &#0034;secure&#0034;) operation that overwrites data with a pattern or as a TAPE_ERASE_SHORT (in other words, a &#0034;quick&#0034;) operation that writes an end-of-recorded-data mark at the current position.
old-location: storage\ioctl_tape_erase.htm
old-project: storage
ms.assetid: 75ec5c40-1ac2-472a-9923-26018eb6267c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.ioctl_tape_erase, IOCTL_TAPE_ERASE control code [Storage Devices], IOCTL_TAPE_ERASE, ntddtape/IOCTL_TAPE_ERASE, k307_cdbe0ea5-0d23-4ab0-9d37-2832d2367b81.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddtape.h
apiname:
-	IOCTL_TAPE_ERASE
product: Windows
targetos: Windows
req.typenames: TAPE_DRIVE_PROBLEM_TYPE
---

# IOCTL_TAPE_ERASE IOCTL
Erases the current tape partition, either as a TAPE_ERASE_LONG (in other words, a "secure") operation that overwrites data with a pattern or as a TAPE_ERASE_SHORT (in other words, a "quick") operation that writes an end-of-recorded-data mark at the current position.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a structure of type <a href="..\ntddtape\ns-ntddtape-_tape_erase.md">TAPE_ERASE</a>. 

If the <b>Immediate</b> member is <b>TRUE</b>, the operation should be asynchronous.

### Input Buffer Length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(TAPE_ERASE).

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_DEVICE_DATA_ERROR, STATUS_NO_SUCH_DEVICE, STATUS_IO_TIMEOUT, STATUS_IO_DEVICE_ERROR, STATUS_MEDIA_WRITE_PROTECTED, STATUS_INSUFFICIENT_RESOURCES, STATUS_NOT_IMPLEMENTED, STATUS_NO_MEDIA_IN_DEVICE, or STATUS_VERIFY_REQUIRED.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddtape.h (include Ntddtape.h) |

## See Also

<a href="..\minitape\ne-minitape-_tape_status.md">TAPE_STATUS</a>



<a href="..\ntddtape\ns-ntddtape-_tape_erase.md">TAPE_ERASE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567933">TapeMiniErase</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_TAPE_ERASE control code%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>