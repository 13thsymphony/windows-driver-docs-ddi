---
UID: NI:ntddpcm.IOCTL_SOCKET_INFORMATION
title: IOCTL_SOCKET_INFORMATION
author: windows-driver-content
description: This request retrieves socket information for the socket that is indicated by the caller.
old-location: pcmcia\ioctl_socket_information.htm
old-project: PCMCIA
ms.assetid: 95563d68-e812-4c62-9668-8cb25b4735aa
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PCMCIA.ioctl_socket_information, IOCTL_SOCKET_INFORMATION control code [Buses], IOCTL_SOCKET_INFORMATION, ntddpcm/IOCTL_SOCKET_INFORMATION, memcdref_8730c03b-fc86-4d43-8aa9-6d15abcfa2d0.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddpcm.h
req.include-header: Ntddpcm.h
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
-	ntddpcm.h
apiname:
-	IOCTL_SOCKET_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PPCMCIA_CONTROLLER_CLASS, PCMCIA_CONTROLLER_CLASS"
---

# IOCTL_SOCKET_INFORMATION IOCTL
This request retrieves socket information for the socket that is indicated by the caller.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(PCMCIA_SOCKET_INFORMATION).

The caller initializes the <b>Socket</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537612">PCMCIA_SOCKET_INFORMATION</a> structure at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

### Input Buffer Length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(PCMCIA_SOCKET_INFORMATION).

### Output Buffer
The PCMCIA bus driver stores the requested socket data in a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537612">PCMCIA_SOCKET_INFORMATION</a> at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

### Output Buffer Length
The size of the requested socket data.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to the number of bytes read. 

If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.

If <b>InputBufferLength</b> is less than <b>sizeof</b>(PCMCIA_SOCKET_INFORMATION), the <b>Status</b> field is set to STATUS_BUFFER_TOO_SMALL.

If <b>OutputBufferLength</b> is less than <b>sizeof</b>(PCMCIA_SOCKET_INFORMATION), the <b>Status</b> field is set to STATUS_BUFFER_TOO_SMALL.

If the bus driver cannot identify a socket that is associated with the socket number indicated in <a href="https://msdn.microsoft.com/library/windows/hardware/ff537612">PCMCIA_SOCKET_INFORMATION</a>, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.

If there is no card in the indicated socket, the <b>Status</b> field is set to STATUS_UNSUCCESSFUL.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddpcm.h (include Ntddpcm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537612">PCMCIA_SOCKET_INFORMATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCMCIA\buses]:%20IOCTL_SOCKET_INFORMATION control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>