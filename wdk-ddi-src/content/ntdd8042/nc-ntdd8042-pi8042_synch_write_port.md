---
UID: NC:ntdd8042.PI8042_SYNCH_WRITE_PORT
title: PI8042_SYNCH_WRITE_PORT
author: windows-driver-content
description: The PI8042_SYNCH_READ_PORT-typed callback routine does a synchronized write to an i8042 port. I8042prt supplies this routine.
old-location: hid\pi8042_synch_write_port.htm
old-project: hid
ms.assetid: f4b0642c-0355-46ae-9c23-fc9c98dfaf21
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: hid.pi8042_synch_write_port, SynchWritePort callback function [Human Input Devices], SynchWritePort, PI8042_SYNCH_WRITE_PORT, PI8042_SYNCH_WRITE_PORT, ntdd8042/SynchWritePort, i8042ref_79e22dfb-4844-4126-a6a2-b2f908cbdf79.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntdd8042.h
req.include-header: Ntdd8042.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ntdd8042.h
apiname:
-	SynchWritePort
product: Windows
targetos: Windows
req.typenames: "*PMSFC_VirtualFibrePortAttributes, MSFC_VirtualFibrePortAttributes"
---


# PI8042_SYNCH_WRITE_PORT callback function
The PI8042_SYNCH_READ_PORT-typed callback routine does a synchronized write to an i8042 port. I8042prt supplies this routine.

## Syntax

```
PI8042_SYNCH_WRITE_PORT Pi8042SynchWritePort;

NTSTATUS Pi8042SynchWritePort(
  PVOID Context,
  UCHAR Value,
  BOOLEAN WaitForACK
)
{...}
```

## Parameters

`Context`

Pointer to a context supplied by I8042prt.

`Value`

Specifies the UCHAR value to write to an i8042 port.

`WaitForACK`

Specifies, if <b>TRUE</b>, that the routine waits until the write is acknowledged by the i8042 port. Otherwise, the routine returns without waiting for an acknowledgment from the port.


## Return Value

The PI8042_SYNCH_WRITE_PORT callback returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The routine successfully wrote a byte to an i8042 port.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IO_TIMEOUT</b></dt>
</dl>
</td>
<td width="60%">
The hardware was not ready for a write access.

</td>
</tr>
</table>

## Remarks

The PI8042_SYNCH_READ_PORT callback can only be used in a <a href="..\ntdd8042\nc-ntdd8042-pi8042_keyboard_initialization_routine.md">PI8042_KEYBOARD_INITIALIZATION_ROUTINE</a> callback. I8042prt specifies the write port callback in the <i>WritePort</i> parameter that I8042prt inputs to a keyboard initialization routine.

The routine polls the hardware until a read is returned by the hardware or an internal time-out occurs.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntdd8042.h (include Ntdd8042.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ntdd8042\nc-ntdd8042-pi8042_synch_read_port.md">PI8042_SYNCH_READ_PORT</a>



<a href="..\ntdd8042\nc-ntdd8042-pi8042_keyboard_initialization_routine.md">PI8042_KEYBOARD_INITIALIZATION_ROUTINE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20PI8042_SYNCH_WRITE_PORT callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>