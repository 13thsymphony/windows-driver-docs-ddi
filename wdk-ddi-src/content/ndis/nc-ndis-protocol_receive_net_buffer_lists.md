---
UID: NC.ndis.PROTOCOL_RECEIVE_NET_BUFFER_LISTS
title: PROTOCOL_RECEIVE_NET_BUFFER_LISTS
author: windows-driver-content
description: The ProtocolReceiveNetBufferLists function processes receive indications from underlying drivers.Note  You must declare the function by using the PROTOCOL_RECEIVE_NET_BUFFER_LISTS type.
old-location: netvista\protocolreceivenetbufferlists.htm
old-project: NetVista
ms.assetid: c964b4b8-ab07-4a07-9965-5cc06c028c20
ms.author: windowsdriverdev
ms.date: 12/14/2017
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
req.alt-api: ProtocolReceiveNetBufferLists
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

# PROTOCOL_RECEIVE_NET_BUFFER_LISTS callback



## -description
The 
  <i>ProtocolReceiveNetBufferLists</i> function processes receive indications from underlying drivers.



## -prototype

````
PROTOCOL_RECEIVE_NET_BUFFER_LISTS ProtocolReceiveNetBufferLists;

VOID ProtocolReceiveNetBufferLists(
  _In_ NDIS_HANDLE      ProtocolBindingContext,
  _In_ PNET_BUFFER_LIST NetBufferLists,
  _In_ NDIS_PORT_NUMBER PortNumber,
  _In_ ULONG            NumberOfNetBufferLists,
  _In_ ULONG            ReceiveFlags
)
{ ... }
````


## -parameters

### -param ProtocolBindingContext [in]

A handle to a context area that the protocol driver allocated to maintain state information for a
     binding. This handle was passed to NDIS in a previous call to the 
     <a href="netvista.ndisopenadapterex">NdisOpenAdapterEx</a> function.


### -param NetBufferLists [in]

A linked list of 
     <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures that the
     underlying driver allocated. Each <b>NET_BUFFER_LIST</b> structure is usually associated with one 
     <a href="netvista.net_buffer">NET_BUFFER</a> structure.


### -param PortNumber [in]

A port number that identifies a miniport adapter port. The default port number of a miniport
     adapter is zero. Protocol drivers that do not use miniport adapter ports should ignore this
     parameter.


### -param NumberOfNetBufferLists [in]

The number of <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures that are in the linked list of structures at 
     <i>NetBufferLists</i> .


### -param ReceiveFlags [in]

Flags that define attributes for the send operation. The flags can be combined with an OR
     operation. To clear all the flags, set this member to zero. This function supports the following flags:
     




### -param NDIS_RECEIVE_FLAGS_DISPATCH_LEVEL

Specifies that the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
       <a href="netvista.dispatch_irql_tracking">Dispatch IRQL Tracking</a>.


### -param NDIS_RECEIVE_FLAGS_RESOURCES

Specifies that NDIS reclaims ownership of the <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures and any attached
       <a href="netvista.net_buffer">NET_BUFFER</a> structures immediately after the call to 
       <i>ProtocolReceiveNetBufferLists</i> returns.


### -param NDIS_RECEIVE_FLAGS_SINGLE_ETHER_TYPE

Specifies that all of the <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> have the same protocol type (EtherType).


### -param NDIS_RECEIVE_FLAGS_SINGLE_VLAN

Specifies that all of the <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> belong to the same VLAN.


### -param NDIS_RECEIVE_FLAGS_PERFECT_FILTERED

Specifies that all of the <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> include only data that matches the packet filter and multicast list that are
       assigned to the miniport adapter.


### -param NDIS_RECEIVE_FLAGS_SINGLE_QUEUE

Specifies that all the <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> belong to the same VM queue. A miniport driver must set this flag for all receive
       indications on a queue if the <b>NDIS_RECEIVE_QUEUE_PARAMETERS_PER_QUEUE_RECEIVE_INDICATION</b> flag was set
       in the 
       <b>Flags</b> member of the 
       <a href="netvista.ndis_receive_queue_parameters">
       NDIS_RECEIVE_QUEUE_PARAMETERS</a> structure when that queue was allocated.


### -param NDIS_RECEIVE_FLAGS_SHARED_MEMORY_INFO_VALID

Specifies that all the <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> contain shared memory information that is valid. When this flag is set on a
       received <b>NET_BUFFER_LIST</b>, NDIS treats the shared memory information as valid. When this flag is not
       set, NDIS and drivers ignore the shared memory information. For example, intermediate drivers that
       modify packet data can use this flag to determine if data should be copied. Miniport drivers can use
       the flag to determine how to free the memory that is associated with a VM queue when a queue is
       deleted.


### -param NDIS_RECEIVE_FLAGS_MORE_NBLS

Reserved.

</dd>
</dl>

## -returns
None


## -remarks
<i>ProtocolReceiveNetBufferLists</i> is a required function for protocol drivers. NDIS calls 
    <i>ProtocolReceiveNetBufferLists</i> after a bound miniport driver calls the 
    <a href="netvista.ndismindicatereceivenetbufferlists">
    NdisMIndicateReceiveNetBufferLists</a> function. A call to 
    <i>ProtocolReceiveNetBufferLists</i> can also occur as a result of a loopback.

If the <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag in the 
    <i>ReceiveFlags</i> parameter is not set, the protocol driver retains ownership of the 
    <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures until it calls
    the 
    <a href="netvista.ndisreturnnetbufferlists">
    NdisReturnNetBufferLists</a> function.

If NDIS sets the <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag the protocol driver cannot retain the
    <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure and associated resources. The set <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag indicates
    that an underlying driver is running low on receive resources. In this case, the 
    <i>ProtocolReceiveNetBufferLists</i> function should copy the received data into protocol-allocated
    storage and return as quickly as possible.

On a multiprocessor system, this function can execute concurrently on more than one processor. Apply
    protection (for example, use spin locks) to critical data structures that are accessed by 
    <i>ProtocolReceiveNetBufferLists</i>.

NDIS calls 
    <i>ProtocolReceiveNetBufferLists</i> at IRQL&lt;= DISPATCH_LEVEL.

To define a <i>ProtocolReceiveNetBufferLists</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolReceiveNetBufferLists</i> function that is named "MyReceiveNetBufferLists", use the <b>PROTOCOL_RECEIVE_NET_BUFFER_LISTS</b> type as shown in this code example:

Then, implement your function as follows:

The <b>PROTOCOL_RECEIVE_NET_BUFFER_LISTS</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_RECEIVE_NET_BUFFER_LISTS</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

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
<a href="netvista.ndis_receive_queue_parameters">NDIS_RECEIVE_QUEUE_PARAMETERS</a>
</dt>
<dt>
<a href="netvista.ndismindicatereceivenetbufferlists">
   NdisMIndicateReceiveNetBufferLists</a>
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
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20PROTOCOL_RECEIVE_NET_BUFFER_LISTS callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

