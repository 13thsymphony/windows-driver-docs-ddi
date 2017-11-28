---
UID: NF.wdm.ExCancelTimer
title: ExCancelTimer
author: windows-driver-content
description: The ExCancelTimer routine cancels a timer that was set by a previous call to the ExSetTimer routine.
old-location: kernel\excanceltimer.htm
old-project: kernel
ms.assetid: 5E52550D-0A81-4C72-9A82-7C13BC3EFE00
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: ExCancelTimer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ExCancelTimer
req.alt-loc: ntoskrnl.lib,ntoskrnl.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# ExCancelTimer function



## -description
<p>The <b>ExCancelTimer</b> routine cancels a timer that was set by a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265188">ExSetTimer</a> routine.</p>


## -syntax

````
BOOLEAN ExCancelTimer(
  _Inout_  PEX_TIMER              Timer,
  _In_opt_ PEXT_CANCEL_PARAMETERS Parameters
);
````


## -parameters
<dl>

### -param <i>Timer</i> [in, out]

<dd>
<p>A pointer to an <a href="kernel.ex_timer">EX_TIMER</a> structure. This structure is a timer object that was previously allocated by the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265179">ExAllocateTimer</a> routine.</p>
</dd>

### -param <i>Parameters</i> [in, optional]

<dd>
<p>Drivers must set this parameter to <b>NULL</b>.</p>
</dd>
</dl>

## -returns
<p>This routine returns <b>TRUE</b> if the timer was canceled. Otherwise, the routine returns <b>FALSE</b>.</p>

## -remarks
<p>After your driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265188">ExSetTimer</a> routine to set the timer, the timer might be canceled before it expires. The driver can call the <b>ExCancelTimer</b> routine to explicitly cancel a pending timer. Also, if the driver calls the <b>ExSetTimer</b> routine to set a new timer on a timer object before a previously set timer on this object expires, this <b>ExSetTimer</b> call implicitly cancels the previous timer and then starts the new timer.</p>

<p>A return value of <b>TRUE</b> indicates that the timer was set when <b>ExCancelTimer</b> was called. In this case, the routine cancels the timer. A return value of <b>FALSE</b> indicates that the timer was not set, which might mean that the timer was never set, that the timer had already been canceled, or that the timer had already expired.</p>

<p>When a timer expires, the operating system signals the timer object. As an option, a driver can supply an <a href="https://msdn.microsoft.com/library/windows/hardware/dn265190">ExTimerCallback</a> callback routine that is called when the timer expires. If the driver supplies this callback routine, this routine is guaranteed to be called if the timer object is signaled. If the timer is canceled before it expires, the timer object is not signaled and the callback routine is not called.</p>

<p>For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265198">ExXxxTimer Routines and EX_TIMER Objects</a>.</p>

<p>After your driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265188">ExSetTimer</a> routine to set the timer, the timer might be canceled before it expires. The driver can call the <b>ExCancelTimer</b> routine to explicitly cancel a pending timer. Also, if the driver calls the <b>ExSetTimer</b> routine to set a new timer on a timer object before a previously set timer on this object expires, this <b>ExSetTimer</b> call implicitly cancels the previous timer and then starts the new timer.</p>

<p>A return value of <b>TRUE</b> indicates that the timer was set when <b>ExCancelTimer</b> was called. In this case, the routine cancels the timer. A return value of <b>FALSE</b> indicates that the timer was not set, which might mean that the timer was never set, that the timer had already been canceled, or that the timer had already expired.</p>

<p>When a timer expires, the operating system signals the timer object. As an option, a driver can supply an <a href="https://msdn.microsoft.com/library/windows/hardware/dn265190">ExTimerCallback</a> callback routine that is called when the timer expires. If the driver supplies this callback routine, this routine is guaranteed to be called if the timer object is signaled. If the timer is canceled before it expires, the timer object is not signaled and the callback routine is not called.</p>

<p>For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265198">ExXxxTimer Routines and EX_TIMER Objects</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 8.1.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ntoskrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265179">ExAllocateTimer</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265188">ExSetTimer</a>
</dt>
<dt>
<a href="kernel.ex_timer">EX_TIMER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExCancelTimer routine%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
