---
UID: NC:ntdd8042.PI8042_SYNCH_WRITE_PORT
title: PI8042_SYNCH_WRITE_PORT
author: windows-driver-content
description: The PI8042_SYNCH_READ_PORT-typed callback routine does a synchronized write to an i8042 port. I8042prt supplies this routine.
old-location: hid\pi8042_synch_write_port.htm
old-project: hid
ms.assetid: f4b0642c-0355-46ae-9c23-fc9c98dfaf21
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PI8042_SYNCH_WRITE_PORT, SynchWritePort, SynchWritePort callback function [Human Input Devices], hid.pi8042_synch_write_port, i8042ref_79e22dfb-4844-4126-a6a2-b2f908cbdf79.xml, ntdd8042/SynchWritePort
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ntdd8042.h
api_name:
-	SynchWritePort
product: Windows
targetos: Windows
req.typenames: MSFC_VirtualFibrePortAttributes, *PMSFC_VirtualFibrePortAttributes
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

The PI8042_SYNCH_READ_PORT callback can only be used in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543243">PI8042_KEYBOARD_INITIALIZATION_ROUTINE</a> callback. I8042prt specifies the write port callback in the <i>WritePort</i> parameter that I8042prt inputs to a keyboard initialization routine.

The routine polls the hardware until a read is returned by the hardware or an internal time-out occurs.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntdd8042.h (include Ntdd8042.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543243">PI8042_KEYBOARD_INITIALIZATION_ROUTINE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543272">PI8042_SYNCH_READ_PORT</a>