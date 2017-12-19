---
UID: NF.ndis.NdisMSynchronizeWithInterruptEx
title: NdisMSynchronizeWithInterruptEx function
author: windows-driver-content
description: Miniport drivers call the NdisMSynchronizeWithInterruptEx function to synchronize the execution of a miniport driver-supplied function with the MiniportInterrupt function.
old-location: netvista\ndismsynchronizewithinterruptex.htm
old-project: NetVista
ms.assetid: 5dca9258-a3ae-43f4-a5aa-d591165d72ed
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisMSynchronizeWithInterruptEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMSynchronizeWithInterruptEx
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: NdisMDeregisterInterruptEx
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DIRQL
---

# NdisMSynchronizeWithInterruptEx function



## -description
Miniport drivers call the
  <b>NdisMSynchronizeWithInterruptEx</b> function to synchronize the execution of a miniport driver-supplied
  function with the 
  <a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a> function.



## -syntax

````
BOOLEAN NdisMSynchronizeWithInterruptEx(
  _In_ NDIS_HANDLE NdisInterruptHandle,
  _In_ ULONG       MessageId,
  _In_ PVOID       SynchronizeFunction,
  _In_ PVOID       SynchronizeContext
);
````


## -parameters

### -param NdisInterruptHandle [in]

An interrupt handle that the miniport driver obtained in a previous call to the 
     <a href="netvista.ndismregisterinterruptex">
     NdisMRegisterInterruptEx</a> function.


### -param MessageId [in]

A message-signaled interrupt with which the driver must synchronize. If NDIS did not grant message
     signaled interrupts for the driver, NDIS ignores this parameter. 
     <i>MessageId</i> is an index to the 
     <a href="kernel.io_interrupt_message_info_entry">
     IO_INTERRUPT_MESSAGE_INFO_ENTRY</a> structures inside a 
     <a href="kernel.io_interrupt_message_info">
     IO_INTERRUPT_MESSAGE_INFO</a> structure. NDIS passes a pointer to the associated
     IO_INTERRUPT_MESSAGE_INFO structure at the 
     <b>MessageInfoTable</b> member when the driver successfully registers for MSI with the 
     <b>NdisMRegisterInterruptEx</b> function.


### -param SynchronizeFunction [in]

The entry point of the driver's 
     <a href="..\ndis\nc-ndis-miniport_synchronize_interrupt.md">
     MiniportSynchronizeInterrupt</a> function.


### -param SynchronizeContext [in]

A pointer to a miniport-driver-determined context area that is passed to the 
     <i>MiniportSynchronizeInterrupt</i> function at 
     <i>SynchronizeContext</i> .


## -returns
<b>NdisMSynchronizeWithInterruptEx</b> returns the Boolean value that 
     <i>MiniportSynchronizeInterrupt</i> returns.


## -remarks
Miniport drivers that register an interrupt with
    <b>NdisMRegisterInterruptEx</b> use
    <b>NdisMSynchronizeWithInterruptEx</b>. The value that the 
    <a href="..\ndis\nc-ndis-miniport_synchronize_interrupt.md">
    MiniportSynchronizeInterrupt</a> function returns is also returned by 
    <b>NdisMSynchronizeWithInterruptEx</b>. This propagated value provides status to the caller.

Any miniport driver function that shares resources with any other driver function that runs at DIRQL
    must use 
    <b>NdisMSynchronizeWithInterruptEx</b> to synchronize its access to those resources. The 
    <i>MiniportSynchronizeInterrupt</i> function also runs at DIRQL, and the shared resources are protected by
    a system-allocated spin lock. Thus, the shared resources are protected from simultaneous access by the 
    <i>MiniportInterrupt</i> function and the caller.

<b>NdisMSynchronizeWithInterruptEx</b> releases the system spin lock and restores the original IRQL of its
    caller before it returns control.

For more information about acquiring and releasing NDIS spin locks, see 
    <a href="netvista.synchronization_and_notification_in_network_drivers">Synchronization
    and Notification in Network Drivers</a>.


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
Supported in NDIS 6.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DIRQL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.ndis_ndismderegisterinterruptex">NdisMDeregisterInterruptEx</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.io_interrupt_message_info">IO_INTERRUPT_MESSAGE_INFO</a>
</dt>
<dt>
<a href="kernel.io_interrupt_message_info_entry">
   IO_INTERRUPT_MESSAGE_INFO_ENTRY</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_synchronize_interrupt.md">
   MiniportSynchronizeInterrupt</a>
</dt>
<dt>
<a href="netvista.ndismregisterinterruptex">NdisMRegisterInterruptEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisMSynchronizeWithInterruptEx function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

