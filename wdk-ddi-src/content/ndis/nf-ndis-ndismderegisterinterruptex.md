---
UID: NF.ndis.NdisMDeregisterInterruptEx
title: NdisMDeregisterInterruptEx function
author: windows-driver-content
description: Miniport drivers call NdisMDeregisterInterruptEx to release resources that were previously allocated with the NdisMRegisterInterruptEx function.
old-location: netvista\ndismderegisterinterruptex.htm
old-project: netvista
ms.assetid: bc0718b6-4c71-41a8-bab6-a52991b284d9
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: NdisMDeregisterInterruptEx
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
req.alt-api: NdisMDeregisterInterruptEx
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Init_DeRegisterInterrupt, Init_RegisterInterrupt, Irql_Interrupt_Function, NdisMDeregisterInterruptEx
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# NdisMDeregisterInterruptEx function



## -description
Miniport drivers call 
  <b>NdisMDeregisterInterruptEx</b> to release resources that were previously allocated with the 
  <a href="netvista.ndismregisterinterruptex">
  NdisMRegisterInterruptEx</a> function.


## -syntax

````
VOID NdisMDeregisterInterruptEx(
  _In_ NDIS_HANDLE NdisInterruptHandle
);
````


## -parameters

### -param NdisInterruptHandle [in]

An interrupt handle that the miniport driver obtained in a previous call to 
     <b>NdisMRegisterInterruptEx</b>.

## -returns
None

## -remarks
<b>NdisMDeregisterInterruptEx</b> releases the resources that were allocated in 
    <b>NdisMRegisterInterruptEx</b>. After 
    <b>NdisMDeregisterInterruptEx</b> returns, NDIS will not call the miniport driver's 
    <a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a> function or 
    <a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a> function.

A miniport driver can call 
    <b>NdisMDeregisterInterruptEx</b> from its 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> or 
    <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> function only if 
    <i>MiniportInitializeEx</i> previously made a successful call to 
    <b>NdisMRegisterInterruptEx</b>.

The miniport driver should disable its NIC from generating interrupts before it calls 
    <b>NdisMDeregisterInterruptEx</b>. After 
    <b>NdisMDeregisterInterruptEx</b> returns control, the miniport driver cannot call the 
    <a href="netvista.ndismsynchronizewithinterruptex">
    NdisMSynchronizeWithInterruptEx</a> function.

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
PASSIVE_LEVEL
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.ndis_init_deregisterinterrupt">Init_DeRegisterInterrupt</a>, <a href="devtest.ndis_init_registerinterrupt">Init_RegisterInterrupt</a>, <a href="devtest.ndis_irql_interrupt_function">Irql_Interrupt_Function</a>, <a href="devtest.ndis_ndismderegisterinterruptex">NdisMDeregisterInterruptEx</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInetrrupt</a>
</dt>
<dt>
<a href="netvista.ndismregisterinterruptex">NdisMRegisterInterruptEx</a>
</dt>
<dt>
<a href="netvista.ndismsynchronizewithinterruptex">
   NdisMSynchronizeWithInterruptEx</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMDeregisterInterruptEx function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
