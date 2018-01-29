---
UID : NI:ntddchgr.IOCTL_CHANGER_SET_POSITION
title : IOCTL_CHANGER_SET_POSITION
author : windows-driver-content
description : Sets the changer's robotic transport mechanism to the specified element address, typically to optimize moving or exchanging media by positioning the transport beforehand.
old-location : storage\ioctl_changer_set_position.htm
old-project : storage
ms.assetid : cd4f5872-d2cb-42ee-b78c-6b7d48d41e34
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ioctl_changer_set_position, IOCTL_CHANGER_SET_POSITION control code [Storage Devices], IOCTL_CHANGER_SET_POSITION, ntddchgr/IOCTL_CHANGER_SET_POSITION, k307_f4580e0a-0f44-4c7f-9d89-81fe6db548c6.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ntddchgr.h
req.include-header : Ntddchgr.h
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
req.typenames : ELEMENT_TYPE, *PELEMENT_TYPE
---

# IOCTL_CHANGER_SET_POSITION IOCTL
Sets the changer's robotic transport mechanism to the specified element address, typically to optimize moving or exchanging media by positioning the transport beforehand.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="..\ntddchgr\ns-ntddchgr-_changer_set_position.md">CHANGER_SET_POSITION</a> structure that specifies the transport to move and the destination. If the <b>Flip</b> member is <b>TRUE</b> and the device supports two-sided media, the media currently carried by the transport should be flipped.

### Input Buffer Length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(CHANGER_SET_POSITION).

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to <b>sizeof</b>(CHANGER_SET_POSITION). The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, STATUS_INVALID_DEVICE_REQUEST, or STATUS_INVALID_PARAMETER.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | ntddchgr.h (include Ntddchgr.h) |
| **IRQL** |  |

## See Also

<a href="..\mcd\nf-mcd-changersetposition.md">ChangerSetPosition</a>

<a href="..\ntddchgr\ns-ntddchgr-_changer_set_position.md">CHANGER_SET_POSITION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CHANGER_SET_POSITION control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>