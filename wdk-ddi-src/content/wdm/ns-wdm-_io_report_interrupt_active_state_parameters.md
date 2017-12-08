---
UID: NS.WDM._IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS
title: _IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS
author: windows-driver-content
description: The IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS structure contains the connection context for a registered interrupt service routine (ISR) that was connected to an interrupt or interrupts by a previous call to the IoConnectInterruptEx routine.
old-location: kernel\io_report_interrupt_active_state_parameters.htm
old-project: kernel
ms.assetid: 430B8951-37F0-4173-ACC6-89DB542B4081
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS, *PIO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS, IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# _IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS structure



## -description
The <b>IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS</b> structure contains the connection context for a registered interrupt service routine (ISR) that was connected to an interrupt or interrupts by a previous call to the <a href="kernel.ioconnectinterruptex">IoConnectInterruptEx</a> routine.


## -syntax

````
typedef struct _IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS {
  ULONG Version;
  union {
    PVOID                      Generic;
    PIO_INTERRUPT_MESSAGE_INFO InterruptMessageTable;
    PKINTERRUPT                InterruptObject;
  } ConnectionContext;
} IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS, *PIO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS;
````


## -struct-fields

### -field Version

The interrupt connection type described by this structure. This member must match the connection type the caller obtained from the <b>IoConnectInterruptEx</b> call that connected the interrupt. The following are valid values for this member:
<ul>
<li>CONNECT_FULLY_SPECIFIED</li>
<li>CONNECT_LINE_BASED</li>
<li>CONNECT_MESSAGE_BASED</li>
<li>CONNECT_FULLY_SPECIFIED_GROUP</li>
</ul>
For more information, see Remarks.

### -field ConnectionContext

A union that contains the connection context associated with the interrupt. Each union member is a pointer to a connection context of a particular type. If <b>Version</b> = CONNECT_MESSAGE_BASED, the <b>InterruptMessageTable</b> member of this union contains a pointer to an <a href="kernel.io_interrupt_message_info">IO_INTERRUPT_MESSAGE_INFO</a> structure. For all other <b>Version</b> values, the <b>InterruptObject</b> member of this union contains a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554237">KINTERRUPT</a> structure. Use the <b>Generic</b> member of this union to treat the connection context pointer as a PVOID value (and avoid casting).
For more information, see Remarks.

### -field Generic

A PVOID pointer to a connection context.

### -field InterruptMessageTable

A pointer to a connection context of type <a href="kernel.io_interrupt_message_info">IO_INTERRUPT_MESSAGE_INFO</a>.

### -field InterruptObject

A pointer to a connection context of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff554237">KINTERRUPT</a>.
</dd>
</dl>

## -remarks
This structure is supplied as a parameter to the <a href="kernel.ioreportinterruptactive">IoReportInterruptActive</a> and <a href="kernel.ioreportinterruptinactive">IoReportInterruptInactive</a> routines.

The <b>Version</b> member indicates the type of the connection context specified in the <b>ConnectionContext</b> member. Set this member to the <i>Parameters-</i>&gt;<b>Version</b> value obtained from the <a href="kernel.ioconnectinterruptex">IoConnectInterruptEx</a> call that connected the interrupt.

If the <i>Parameters-</i>&gt;<b>Version</b> value obtained from <b>IoConnectInterruptEx</b> is CONNECT_FULLY_SPECIFIED or CONNECT_FULLY_SPECIFIED_GROUP, set the <b>ConnectionContext.InterruptObject</b> member of the <b>IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS</b> structure to the *(<i>Parameters-</i>&gt;<b>FullySpecified.InterruptObject</b>) pointer value obtained from <b>IoConnectInterruptEx</b>.

If the <i>Parameters-</i>&gt;<b>Version</b> value obtained from <b>IoConnectInterruptEx</b> is CONNECT_MESSAGE_BASED, set the <b>ConnectionContext.InterruptMessageTable</b> member of the <b>IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS</b> structure to the *(<i>Parameters-</i>&gt;<b>MessageBased.ConnectionContext.InterruptMessageTable</b>) pointer value obtained from <b>IoConnectInterruptEx</b>.

If the <i>Parameters-</i>&gt;<b>Version</b> value obtained from <b>IoConnectInterruptEx</b> is CONNECT_LINE_BASED, but the caller initially set <i>Parameters-</i>&gt;<b>Version</b> to CONNECT_MESSAGE_BASED, set the <b>ConnectionContext.InterruptObject</b> member of the <b>IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS</b> structure to the *(<i>Parameters-</i>&gt;<b>MessageBased.ConnectionContext.InterruptObject</b>) pointer value obtained from <b>IoConnectInterruptEx</b>.

If the <i>Parameters-</i>&gt;<b>Version</b> value obtained from <b>IoConnectInterruptEx</b> is CONNECT_LINE_BASED, and the caller initially set <i>Parameters-</i>&gt;<b>Version</b> to CONNECT_LINE_BASED, set the <b>ConnectionContext.InterruptObject</b> member of the <b>IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS</b> structure to the *(<i>Parameters-</i>&gt;<b>LineBased.InterruptObject</b>) pointer value obtained from <b>IoConnectInterruptEx</b>.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.ioconnectinterruptex">IoConnectInterruptEx</a>
</dt>
<dt>
<a href="kernel.ioreportinterruptactive">IoReportInterruptActive</a>
</dt>
<dt>
<a href="kernel.ioreportinterruptinactive">IoReportInterruptInactive</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
