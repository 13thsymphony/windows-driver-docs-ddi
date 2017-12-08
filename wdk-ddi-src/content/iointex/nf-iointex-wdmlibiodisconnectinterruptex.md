---
UID: NF.iointex.WdmlibIoDisconnectInterruptEx
title: WdmlibIoDisconnectInterruptEx function
author: windows-driver-content
description: The WdmlibIoDisconnectInterruptEx function unregisters an interrupt service routine (ISR) that was registered by a previous call to the WdmlibIoConnectInterruptEx function.
old-location: kernel\wdmlibiodisconnectinterruptex.htm
old-project: kernel
ms.assetid: B6F8663C-3A13-45DA-80FE-CC8B9194D083
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: WdmlibIoDisconnectInterruptEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: iointex.h
req.include-header: Iointex.h, Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista. Drivers that must also work Microsoft Windows 2000, Windows XP, or Windows Server 2003 can instead link to Iointex.lib to use the routine.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WdmlibIoDisconnectInterruptEx,IoDisconnectInterruptEx
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib; Iointex.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
---

# WdmlibIoDisconnectInterruptEx function



## -description
The  <b>WdmlibIoDisconnectInterruptEx</b> function unregisters an interrupt service routine (ISR) that was registered by a previous call to the <a href="kernel.wdmlibioconnectinterruptex">WdmlibIoConnectInterruptEx</a> function.


## -syntax

````
VOID WdmlibIoDisconnectInterruptEx(
  _Inout_ PIO_DISCONNECT_INTERRUPT_PARAMETERS Parameters
);
````


## -parameters

### -param Parameters [in, out]

Pointer to an <a href="kernel.io_disconnect_interrupt_parameters">IO_DISCONNECT_INTERRUPT_PARAMETERS</a> structure that contains the connection context for  the interrupt being disconnected.

## -returns
None.

## -remarks
The driver should configure the device to issue interrupts only when these interrupts are connected. Failure to prevent a device from issuing interrupts when the interrupts are disconnected might cause system instability. For example, if a device shares a level-triggered interrupt line with other devices, and the device issues an interrupt request when the device's interrupts are disconnected, the other devices on the line will not acknowledge the interrupt and the interrupt will continue to fire. Before calling <b>WdmlibIoDisconnectInterruptEx</b>, the driver should configure the device to stop issuing interrupts. After calling <a href="kernel.wdmlibioconnectinterruptex">WdmlibIoConnectInterruptEx</a>, the driver should configure the device to start issuing interrupts.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available starting with Windows Vista. Drivers that must also work Microsoft Windows 2000, Windows XP, or Windows Server 2003 can instead link to Iointex.lib to use the routine.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Iointex.h (include Iointex.h, Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib; </dt>
<dt>Iointex.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
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
<a href="kernel.io_disconnect_interrupt_parameters">IO_DISCONNECT_INTERRUPT_PARAMETERS</a>
</dt>
<dt>
<a href="kernel.wdmlibioconnectinterruptex">WdmlibIoConnectInterruptEx</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WdmlibIoDisconnectInterruptEx function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
