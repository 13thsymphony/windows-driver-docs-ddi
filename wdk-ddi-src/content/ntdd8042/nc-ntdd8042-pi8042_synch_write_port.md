---
UID: NC.ntdd8042.PI8042_SYNCH_WRITE_PORT
title: PI8042_SYNCH_WRITE_PORT
author: windows-driver-content
description: The PI8042_SYNCH_READ_PORT-typed callback routine does a synchronized write to an i8042 port. I8042prt supplies this routine.
old-location: hid\pi8042_synch_write_port.htm
old-project: hid
ms.assetid: f4b0642c-0355-46ae-9c23-fc9c98dfaf21
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _MSFC_VirtualFibrePortAttributes, MSFC_VirtualFibrePortAttributes, *PMSFC_VirtualFibrePortAttributes
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
req.alt-api: SynchWritePort
req.alt-loc: ntdd8042.h
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
---

# PI8042_SYNCH_WRITE_PORT callback



## -description
The PI8042_SYNCH_READ_PORT-typed callback routine does a synchronized write to an i8042 port. I8042prt supplies this routine.



## -prototype

````
PI8042_SYNCH_WRITE_PORT SynchWritePort;

NTSTATUS SynchWritePort(
  _In_ PVOID   Context,
  _In_ UCHAR   Value,
  _In_ BOOLEAN WaitForACK
)
{ ... }
````


## -parameters

### -param Context [in]

Pointer to a context supplied by I8042prt. 


### -param Value [in]

Specifies the UCHAR value to write to an i8042 port.


### -param WaitForACK [in]

Specifies, if <b>TRUE</b>, that the routine waits until the write is acknowledged by the i8042 port. Otherwise, the routine returns without waiting for an acknowledgment from the port.


## -returns
The PI8042_SYNCH_WRITE_PORT callback returns one of the following status values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The routine successfully wrote a byte to an i8042 port.
<dl>
<dt><b>STATUS_IO_TIMEOUT</b></dt>
</dl>The hardware was not ready for a write access.

 


## -remarks
The PI8042_SYNCH_READ_PORT callback can only be used in a <a href="..\ntdd8042\nc-ntdd8042-pi8042_keyboard_initialization_routine.md">PI8042_KEYBOARD_INITIALIZATION_ROUTINE</a> callback. I8042prt specifies the write port callback in the <i>WritePort</i> parameter that I8042prt inputs to a keyboard initialization routine.

The routine polls the hardware until a read is returned by the hardware or an internal time-out occurs.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntdd8042.h (include Ntdd8042.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntdd8042\nc-ntdd8042-pi8042_keyboard_initialization_routine.md">PI8042_KEYBOARD_INITIALIZATION_ROUTINE</a>
</dt>
<dt>
<a href="..\ntdd8042\nc-ntdd8042-pi8042_synch_read_port.md">PI8042_SYNCH_READ_PORT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20PI8042_SYNCH_WRITE_PORT callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

