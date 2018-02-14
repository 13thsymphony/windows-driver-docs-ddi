---
UID: NI:ntddser.IOCTL_SERIAL_SET_BREAK_OFF
title: IOCTL_SERIAL_SET_BREAK_OFF
author: windows-driver-content
description: The IOCTL_SERIAL_SET_BREAK_OFF request sets the line control break signal inactive.
old-location: serports\ioctl_serial_set_break_off.htm
old-project: serports
ms.assetid: aa64da58-cb50-485e-afbc-3a0408b4ecf2
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.ioctl_serial_set_break_off, IOCTL_SERIAL_SET_BREAK_OFF control code [Serial Ports], IOCTL_SERIAL_SET_BREAK_OFF, ntddser/IOCTL_SERIAL_SET_BREAK_OFF, serref_1a347f28-6dfb-4b5d-afb8-9bb8ffad9f36.xml
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
-	IOCTL_SERIAL_SET_BREAK_OFF
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_SET_BREAK_OFF IOCTL
The <b>IOCTL_SERIAL_SET_BREAK_OFF</b> request sets the line control break signal inactive.

To set the line control break signal active, a client can use an <a href="..\ntddser\ni-ntddser-ioctl_serial_set_break_on.md">IOCTL_SERIAL_SET_BREAK_ON</a> request.

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
The <b>Information</b> member is set to zero.

The <b>Status</b> member is to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddser.h (include Ntddser.h) |

## See Also

<a href="..\ntddser\ni-ntddser-ioctl_serial_set_break_on.md">IOCTL_SERIAL_SET_BREAK_ON</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20IOCTL_SERIAL_SET_BREAK_OFF control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>