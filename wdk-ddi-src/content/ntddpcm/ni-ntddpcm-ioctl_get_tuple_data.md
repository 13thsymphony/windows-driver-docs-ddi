---
UID: NI:ntddpcm.IOCTL_GET_TUPLE_DATA
title: IOCTL_GET_TUPLE_DATA
author: windows-driver-content
description: This request retrieves tuple data that is stored in a PC Card's or CardBus card's attribute memory.
old-location: pcmcia\ioctl_get_tuple_data.htm
old-project: PCMCIA
ms.assetid: 90bb06c3-2975-4290-b6f1-0c36e7b8678b
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PCMCIA.ioctl_get_tuple_data, IOCTL_GET_TUPLE_DATA control code [Buses], IOCTL_GET_TUPLE_DATA, ntddpcm/IOCTL_GET_TUPLE_DATA, memcdref_80c1671e-c0c2-4429-b703-ffb389cc7af5.xml
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
-	IOCTL_GET_TUPLE_DATA
product: Windows
targetos: Windows
req.typenames: PCMCIA_CONTROLLER_CLASS, *PPCMCIA_CONTROLLER_CLASS
---

# IOCTL_GET_TUPLE_DATA IOCTL
This request retrieves tuple data that is stored in a PC Card's or CardBus card's attribute memory. The caller must specify the number of the socket where the PC Card or CardBus card is inserted, the location of an output buffer, and the number of bytes of tuple data to be read.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The caller initializes the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538895">TUPLE_REQUEST</a> structure, which is defined in <i>ntddpcm.h</i>, at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

### Input Buffer Length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to <b>sizeof</b>(TUPLE_REQUEST).

### Output Buffer
The PCMCIA bus driver stores the requested tuple data at the beginning of the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

### Output Buffer Length
The size of the requested tuple data.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to the number of bytes read. 

If the operation is successful, the <b>Status</b> field is set to STATUS_SUCCESS.

If <b>InputBufferLength</b> is less than <b>sizeof</b>(TUPLE_REQUEST), the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.

If the bus driver cannot identify a socket that is associated with the socket number indicated in TUPLE_REQUEST, the <b>Status</b> field is set to STATUS_INVALID_PARAMETER.

If there is no card in the indicated socket, the <b>Status</b> field is set to STATUS_UNSUCCESSFUL.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddpcm.h (include Ntddpcm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551769">IRP_MN_WRITE_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551727">IRP_MN_READ_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538895">TUPLE_REQUEST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCMCIA\buses]:%20IOCTL_GET_TUPLE_DATA control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>