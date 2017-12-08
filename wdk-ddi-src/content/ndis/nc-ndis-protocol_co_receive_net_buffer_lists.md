---
UID: NC.ndis.PROTOCOL_CO_RECEIVE_NET_BUFFER_LISTS
title: PROTOCOL_CO_RECEIVE_NET_BUFFER_LISTS
author: windows-driver-content
description: The ProtocolCoReceiveNetBufferLists function processes receive indications from underlying drivers.Note  You must declare the function by using the PROTOCOL_CO_RECEIVE_NET_BUFFER_LISTS type.
old-location: netvista\protocolcoreceivenetbufferlists.htm
old-project: netvista
ms.assetid: 1755804c-d82f-465d-862f-8a2340516f8e
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProtocolCoReceiveNetBufferLists
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# PROTOCOL_CO_RECEIVE_NET_BUFFER_LISTS callback



## -description
The 
  <i>ProtocolCoReceiveNetBufferLists</i> function processes receive indications from underlying
  drivers.


## -prototype

````
PROTOCOL_CO_RECEIVE_NET_BUFFER_LISTS ProtocolCoReceiveNetBufferLists;

VOID ProtocolCoReceiveNetBufferLists(
  _In_ NDIS_HANDLE        ProtocolBindingContext,
  _In_ NDIS_HANDLE        ProtocolVcContext,
  _In_ INPNET_BUFFER_LIST NetBufferLists,
  _In_ ULONG              NumberOfNetBufferLists,
  _In_ ULONG              ReceiveFlags
)
{ ... }
````


## -parameters

### -param ProtocolBindingContext [in]

A handle to a context area that the protocol driver allocated to maintain state information for a
     binding. This handle was passed to NDIS in a previous call to 
     <a href="netvista.ndisopenadapterex">NdisOpenAdapterEx</a>.

### -param ProtocolVcContext [in]

A handle to a protocol driver-allocated context area in which this driver maintains the
     per-virtual connection (VC) run-time state information. A client or stand-alone call manager supplied
     this handle either when it called the 
     <a href="netvista.ndiscocreatevc">NdisCoCreateVc</a> function or from its 
     <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> function.

### -param NetBufferLists [in]

A linked list of 
     <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures that the
     underlying driver allocated. Each <b>NET_BUFFER_LIST</b> structure is usually associated with one 
     <a href="netvista.net_buffer">NET_BUFFER</a> structure.

### -param NumberOfNetBufferLists [in]

The number of <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures that are in the linked list of structures that 
     <i>NetBufferLists</i> specifies.

### -param ReceiveFlags [in]

Flags that define attributes for the send operation. The flags can be combined with a bitwise OR
     operation. To clear all of the flags, set this parameter to zero. 
     <i>ProtocolCoReceiveNetBufferLists</i> supports the following flags:
     


### -param NDIS_RECEIVE_FLAGS_DISPATCH_LEVEL

The current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
       <a href="netvista.dispatch_irql_tracking">Dispatch IRQL Tracking</a>.

### -param NDIS_RECEIVE_FLAGS_RESOURCES

NDIS reclaims ownership of the <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures and any attached NET_BUFFER structures
       immediately after the call to 
       <i>ProtocolCoReceiveNetBufferLists</i> returns.
</dd>
</dl>

## -returns
None

## -remarks
The 
    <i>ProtocolCoReceiveNetBufferLists</i> function is required for CoNDIS protocol drivers. NDIS calls 
    <i>ProtocolCoReceiveNetBufferLists</i> after a bound miniport driver calls the 
    <a href="netvista.ndismcoindicatereceivenetbufferlists">
    NdisMCoIndicateReceiveNetBufferLists</a> function. A call to 
    <i>ProtocolCoReceiveNetBufferLists</i> can also occur as a result of a loopback.

If the <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag in the 
    <i>CoReceiveFlags</i> parameter is not set, the protocol driver retains ownership of the 
    <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures until it calls
    the 
    <a href="netvista.ndisreturnnetbufferlists">
    NdisReturnNetBufferLists</a> function. If NDIS sets the <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag, the protocol
    driver cannot retain the <b>NET_BUFFER_LIST</b> structure and associated resources. <b>NDIS_RECEIVE_FLAGS_RESOURCES</b>
    indicates that an underlying driver has low receive resources. In this case, the 
    <i>ProtocolCoReceiveNetBufferLists</i> function should copy the received data into protocol-allocated
    storage and return as quickly as possible.

On a multiprocessor system, 
    <i>ProtocolCoReceiveNetBufferLists</i> can run concurrently on more than one processor. In this situation,
    apply protection (for example, use spin locks) to critical data structures that 
    <i>ProtocolCoReceiveNetBufferLists</i> accesses.

NDIS calls 
    <i>ProtocolCoReceiveNetBufferLists</i> at IRQL&lt;= DISPATCH_LEVEL.

To define a <i>ProtocolCoReceiveNetBufferLists</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCoReceiveNetBufferLists</i> function that is named "MyCoReceiveNetBufferLists", use the <b>PROTOCOL_CO_RECEIVE_NET_BUFFER_LISTS</b> type as shown in this code example:

Then, implement your function as follows:

The <b>PROTOCOL_CO_RECEIVE_NET_BUFFER_LISTS</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CO_RECEIVE_NET_BUFFER_LISTS</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 

## -requirements
<table>
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
IRQL
</th>
<td width="70%">
&lt;= DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_return_net_buffer_lists.md">
   MiniportReturnNetBufferLists</a>
</dt>
<dt>
<a href="netvista.ndiscocreatevc">NdisCoCreateVc</a>
</dt>
<dt>
<a href="netvista.ndismcoindicatereceivenetbufferlists">
   NdisMCoIndicateReceiveNetBufferLists</a>
</dt>
<dt>
<a href="netvista.ndisopenadapterex">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="netvista.ndisreturnnetbufferlists">NdisReturnNetBufferLists</a>
</dt>
<dt>
<a href="netvista.net_buffer">NET_BUFFER</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_send_net_buffer_lists_complete.md">ProtocolCoSendNetBufferListsComplete</a>
</dt>
<dt>
<a href="netvista.condis_protocol_driver_send_and_receive_functions">CoNDIS Protocol Driver Send and Receive Functions</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CO_RECEIVE_NET_BUFFER_LISTS callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
