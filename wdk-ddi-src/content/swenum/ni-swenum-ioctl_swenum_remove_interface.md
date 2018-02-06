---
UID: NI:swenum.IOCTL_SWENUM_REMOVE_INTERFACE
title: IOCTL_SWENUM_REMOVE_INTERFACE
author: windows-driver-content
description: 
old-location: stream\ioctl_swenum_remove_interface.htm
old-project: stream
ms.assetid: 89E7498F-8568-4A24-8731-E84AC8D1CE94
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ioctl_swenum_remove_interface, IOCTL_SWENUM_REMOVE_INTERFACE control code [Streaming Media Devices], IOCTL_SWENUM_REMOVE_INTERFACE, swenum/IOCTL_SWENUM_REMOVE_INTERFACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: swenum.h
req.include-header: 
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
-	swenum.h
apiname:
-	IOCTL_SWENUM_REMOVE_INTERFACE
product: Windows
targetos: Windows
req.typenames: STREAM_TIME_REFERENCE, *PSTREAM_TIME_REFERENCE
req.product: Windows 10 or later.
---

# IOCTL_SWENUM_REMOVE_INTERFACE IOCTL


### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer


### Input Buffer Length
None

### Output Buffer


### Output Buffer Length


### Input / Output Buffer


### Input / Output Buffer Length


### Status Block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | swenum.h |

## See Also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IOCTL_SWENUM_REMOVE_INTERFACE control code%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>