---
UID: NI:ntddser.IOCTL_SERIAL_GET_DTRRTS
title: IOCTL_SERIAL_GET_DTRRTS
author: windows-driver-content
description: The IOCTL_SERIAL_GET_DTRRTS request returns information about the data terminal ready (DTR) control signal and the request to send (RTS) control signal.
old-location: serports\ioctl_serial_get_dtrrts.htm
old-project: serports
ms.assetid: 9ced72c6-24f8-49c6-a68e-2b0c5c81a8c2
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: serports.ioctl_serial_get_dtrrts, IOCTL_SERIAL_GET_DTRRTS control code [Serial Ports], IOCTL_SERIAL_GET_DTRRTS, ntddser/IOCTL_SERIAL_GET_DTRRTS, serref_7c57fa0a-a5a3-41cd-bea3-b4685b39daad.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddser.h
req.include-header: Ntddser.h
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
-	Ntddser.h
apiname:
-	IOCTL_SERIAL_GET_DTRRTS
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_GET_DTRRTS IOCTL
The <b>IOCTL_SERIAL_GET_DTRRTS</b> request returns information about the <i>data terminal ready</i> (DTR) control signal and the <i>request to send</i> (RTS) control signal.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated ULONG buffer that Serial.sys uses to output information about the DTR and RTS. The ULONG buffer is set to zero or to the bitwise-OR of one or more of the following flag bits:

### Output Buffer Length
The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size in bytes of a ULONG.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the request is successful, the <b>Information</b> member is set to the size in bytes of a ULONG. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddser.h (include Ntddser.h) |

## See Also

<a href="..\ntddser\ni-ntddser-ioctl_serial_set_rts.md">IOCTL_SERIAL_SET_RTS</a>



<a href="..\ntddser\ni-ntddser-ioctl_serial_set_dtr.md">IOCTL_SERIAL_SET_DTR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20IOCTL_SERIAL_GET_DTRRTS control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>