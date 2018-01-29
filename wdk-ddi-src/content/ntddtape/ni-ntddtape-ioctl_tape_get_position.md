---
UID : NI:ntddtape.IOCTL_TAPE_GET_POSITION
title : IOCTL_TAPE_GET_POSITION
author : windows-driver-content
description : Returns the current absolute, logical, or pseudological partition and offset position on the tape.
old-location : storage\ioctl_tape_get_position.htm
old-project : storage
ms.assetid : 358c3089-7238-4604-add8-575b611b3bc9
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ioctl_tape_get_position, IOCTL_TAPE_GET_POSITION control code [Storage Devices], IOCTL_TAPE_GET_POSITION, ntddtape/IOCTL_TAPE_GET_POSITION, k307_88069692-1167-4a21-914b-505e1100f6dc.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ntddtape.h
req.include-header : Ntddtape.h
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
req.typenames : TAPE_DRIVE_PROBLEM_TYPE
---

# IOCTL_TAPE_GET_POSITION IOCTL
Returns the current absolute, logical, or pseudological partition and offset position on the tape.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
The driver returns the <a href="..\ntddtape\ns-ntddtape-_tape_get_position.md">TAPE_GET_POSITION</a> data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

### Output Buffer Length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(TAPE_GET_POSITION).

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_IO_DEVICE_ERROR, STATUS_DEVICE_DATA_ERROR, STATUS_NO_SUCH_DEVICE, STATUS_IO_TIMEOUT, STATUS_DEVICE_NOT_READY, STATUS_NO_MEDIA_IN_DEVICE, or STATUS_VERIFY_REQUIRED.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | ntddtape.h (include Ntddtape.h) |
| **IRQL** |  |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567946">TapeMiniGetPosition</a>

<a href="..\minitape\ne-minitape-_tape_status.md">TAPE_STATUS</a>

<a href="..\ntddtape\ns-ntddtape-_tape_get_position.md">TAPE_GET_POSITION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_TAPE_GET_POSITION control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>