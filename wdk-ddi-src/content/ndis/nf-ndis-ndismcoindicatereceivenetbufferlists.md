---
UID: NF.ndis.NdisMCoIndicateReceiveNetBufferLists
title: NdisMCoIndicateReceiveNetBufferLists function
author: windows-driver-content
description: The NdisMCoIndicateReceiveNetBufferLists function indicates that the miniport driver received data from the network.
old-location: netvista\ndismcoindicatereceivenetbufferlists.htm
old-project: netvista
ms.assetid: dabd472f-9877-4434-a534-e07a047e092f
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: NdisMCoIndicateReceiveNetBufferLists
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMCoIndicateReceiveNetBufferLists
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_MCO_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# NdisMCoIndicateReceiveNetBufferLists function



## -description
The 
  <b>NdisMCoIndicateReceiveNetBufferLists</b> function indicates that the miniport driver received data from
  the network.


## -syntax

````
VOID NdisMCoIndicateReceiveNetBufferLists(
  _In_ NDIS_HANDLE      NdisVcHandle,
  _In_ PNET_BUFFER_LIST NetBufferLists,
  _In_ ULONG            NumberOfNetBufferLists,
  _In_ ULONG            CoReceiveFlags
);
````


## -parameters

### -param NdisVcHandle [in]

A handle that identifies a virtual connection (VC). The miniport driver obtained this handle as an
     input parameter to its 
     <a href="..\ndis\nc-ndis-miniport_co_create_vc.md">MiniportCoCreateVc</a> function, either
     when a client set up an outgoing call or when the call manager created a VC for a client-registered
     service access point (SAP) to indicate an incoming-call notification on.

### -param NetBufferLists [in]

A linked list of 
     <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures that the
     miniport driver allocated.

### -param NumberOfNetBufferLists [in]

The number of NET_BUFFER_LIST structures that are in the linked list of structures that 
     <i>NetBufferLists</i> specifies.

### -param CoReceiveFlags [in]

Flags that define attributes for the send operation. The flags can be combined with a bitwise OR
     operation. To clear all of the flags, set this parameter to zero. 
     <b>NdisMCoIndicateReceiveNetBufferLists</b> supports the following flags:
     


### -param NDIS_RECEIVE_FLAGS_DISPATCH_LEVEL

The current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
       <a href="netvista.dispatch_irql_tracking">Dispatch IRQL Tracking</a>.

### -param NDIS_RECEIVE_FLAGS_RESOURCES

The miniport driver reclaims ownership of the NET_BUFFER_LIST structures and any attached
       NET_BUFFER structures immediately after 
       <b>NdisMCoIndicateReceiveNetBufferLists</b> returns.
</dd>
</dl>

## -returns
None

## -remarks
A miniport driver typically calls the 
    <b>NdisMCoIndicateReceiveNetBufferLists</b> function from its 
    <a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a> function.
    When a miniport driver calls 
    <b>NdisMCoIndicateReceiveNetBufferLists</b>, it specifies a list of 
    <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures at the 
    <i>NetBufferLists</i> parameter. NDIS then passes the NET_BUFFER_LIST structures to bound protocol drivers.

Miniport drivers must set the 
    <b>SourceHandle</b> member of each NET_BUFFER_LIST structure to the same value as the 
    <i>NdisVcHandle</i> parameter so that NDIS can return the NET_BUFFER_LIST structures to the correct
    miniport driver.

If a miniport driver calls 
    <b>NdisMCoIndicateReceiveNetBufferLists</b> and clears the NDIS_RECEIVE_FLAGS_RESOURCES flag in the 
    <i>CoReceiveFlags</i> parameter, NDIS returns the NET_BUFFER_LIST structures that 
    <i>NetBufferLists</i> specifies to the miniport driver's 
    <a href="..\ndis\nc-ndis-miniport_return_net_buffer_lists.md">
    MiniportReturnNetBufferLists</a> function. In this case, the miniport driver must not reclaim the
    NET_BUFFER_LIST structures until NDIS returns the NET_BUFFER_LIST structures to the miniport driver's 
    <i>MiniportReturnNetBufferLists</i> function.

If a miniport driver calls 
    <b>NdisMCoIndicateReceiveNetBufferLists</b> and sets the NDIS_RECEIVE_FLAGS_RESOURCES flag in the 
    <i>CoReceiveFlags</i> parameter, the miniport driver must regain ownership of the NET_BUFFER_LIST
    structures immediately. In this case, NDIS does not call the miniport driver's 
    <i>MiniportReturnNetBufferLists</i> function to return the NET_BUFFER_LIST structures. Instead, NDIS
    returns the NET_BUFFER_LIST structures to the miniport driver when 
    <b>NdisMCoIndicateReceiveNetBufferLists</b> returns. The miniport driver should reclaim the
    NET_BUFFER_LIST structures immediately after 
    <b>NdisMCoIndicateReceiveNetBufferLists</b> returns. To reclaim the NET_BUFFER_LIST structures, a miniport
    driver can call its own 
    <a href="..\ndis\nc-ndis-miniport_return_net_buffer_lists.md">
    MiniportReturnNetBufferLists</a> function.

If a miniport driver sets the NDIS_RECEIVE_FLAGS_RESOURCES flag in the 
    <i>CoReceiveFlags</i> parameter, the protocol drivers must copy the network data and release the
    NET_BUFFER_LIST structures to the miniport driver. You should design your miniport drivers with enough
    preallocated NET_BUFFER_LIST structures to avoid unnecessary copying.

The caller of 
    <b>NdisMCoIndicateReceiveNetBufferLists</b> must properly initialize the NET_BUFFER_LIST structures, the
    attached 
    <a href="netvista.net_buffer">NET_BUFFER</a> structures, and any attached memory
    descriptor lists (MDLs).

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
&lt;= DISPATCH_LEVEL
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.ndis_irql_mco_function">Irql_MCO_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_co_create_vc.md">MiniportCoCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_return_net_buffer_lists.md">
   MiniportReturnNetBufferLists</a>
</dt>
<dt>
<a href="netvista.net_buffer">NET_BUFFER</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCoIndicateReceiveNetBufferLists function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
