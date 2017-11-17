---
UID: NC.ndis.PROTOCOL_RECEIVE_NET_BUFFER_LISTS
title: PROTOCOL_RECEIVE_NET_BUFFER_LISTS
author: windows-driver-content
description: The ProtocolReceiveNetBufferLists function processes receive indications from underlying drivers.Note  You must declare the function by using the PROTOCOL_RECEIVE_NET_BUFFER_LISTS type.
old-location: netvista\protocolreceivenetbufferlists.htm
ms.assetid: c964b4b8-ab07-4a07-9965-5cc06c028c20
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: netvista
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
ms.keywords: RxNameCacheInitialize
req.iface: 
---

# PROTOCOL_RECEIVE_NET_BUFFER_LISTS callback



## -description
<p>The 
  <i>ProtocolReceiveNetBufferLists</i> function processes receive indications from underlying drivers.</p>


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
<dl>

### -param <i>ProtocolBindingContext</i> [in]

<dd>
<p>A handle to a context area that the protocol driver allocated to maintain state information for a
     binding. This handle was passed to NDIS in a previous call to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function.</p>
</dd>

### -param <i>NetBufferLists</i> [in]

<dd>
<p>A linked list of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures that the
     underlying driver allocated. Each <b>NET_BUFFER_LIST</b> structure is usually associated with one 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure.</p>
</dd>

### -param <i>PortNumber</i> [in]

<dd>
<p>A port number that identifies a miniport adapter port. The default port number of a miniport
     adapter is zero. Protocol drivers that do not use miniport adapter ports should ignore this
     parameter.</p>
</dd>

### -param <i>NumberOfNetBufferLists</i> [in]

<dd>
<p>The number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures that are in the linked list of structures at 
     <i>NetBufferLists</i> .</p>
</dd>

### -param <i>ReceiveFlags</i> [in]

<dd>
<p>Flags that define attributes for the send operation. The flags can be combined with an OR
     operation. To clear all the flags, set this member to zero. This function supports the following flags:
     </p>
<p></p>
<dl>

### -param <a id="NDIS_RECEIVE_FLAGS_DISPATCH_LEVEL"></a><a id="ndis_receive_flags_dispatch_level"></a>NDIS_RECEIVE_FLAGS_DISPATCH_LEVEL

<dd>
<p>Specifies that the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
       <a href="NULL">Dispatch IRQL Tracking</a>.</p>
</dd>

### -param <a id="NDIS_RECEIVE_FLAGS_RESOURCES"></a><a id="ndis_receive_flags_resources"></a>NDIS_RECEIVE_FLAGS_RESOURCES

<dd>
<p>Specifies that NDIS reclaims ownership of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures and any attached
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures immediately after the call to 
       <i>ProtocolReceiveNetBufferLists</i> returns.</p>
</dd>

### -param <a id="NDIS_RECEIVE_FLAGS_SINGLE_ETHER_TYPE"></a><a id="ndis_receive_flags_single_ether_type"></a>NDIS_RECEIVE_FLAGS_SINGLE_ETHER_TYPE

<dd>
<p>Specifies that all of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> have the same protocol type (EtherType).</p>
</dd>

### -param <a id="NDIS_RECEIVE_FLAGS_SINGLE_VLAN"></a><a id="ndis_receive_flags_single_vlan"></a>NDIS_RECEIVE_FLAGS_SINGLE_VLAN

<dd>
<p>Specifies that all of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> belong to the same VLAN.</p>
</dd>

### -param <a id="NDIS_RECEIVE_FLAGS_PERFECT_FILTERED"></a><a id="ndis_receive_flags_perfect_filtered"></a>NDIS_RECEIVE_FLAGS_PERFECT_FILTERED

<dd>
<p>Specifies that all of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> include only data that matches the packet filter and multicast list that are
       assigned to the miniport adapter.</p>
</dd>

### -param <a id="NDIS_RECEIVE_FLAGS_SINGLE_QUEUE"></a><a id="ndis_receive_flags_single_queue"></a>NDIS_RECEIVE_FLAGS_SINGLE_QUEUE

<dd>
<p>Specifies that all the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> belong to the same VM queue. A miniport driver must set this flag for all receive
       indications on a queue if the <b>NDIS_RECEIVE_QUEUE_PARAMETERS_PER_QUEUE_RECEIVE_INDICATION</b> flag was set
       in the 
       <b>Flags</b> member of the 
       <a href="https://msdn.microsoft.com/fba87554-766d-45e2-8257-584ee78dd873">
       NDIS_RECEIVE_QUEUE_PARAMETERS</a> structure when that queue was allocated.</p>
</dd>

### -param <a id="NDIS_RECEIVE_FLAGS_SHARED_MEMORY_INFO_VALID"></a><a id="ndis_receive_flags_shared_memory_info_valid"></a>NDIS_RECEIVE_FLAGS_SHARED_MEMORY_INFO_VALID

<dd>
<p>Specifies that all the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures in the list at 
       <i>NetBufferLists</i> contain shared memory information that is valid. When this flag is set on a
       received <b>NET_BUFFER_LIST</b>, NDIS treats the shared memory information as valid. When this flag is not
       set, NDIS and drivers ignore the shared memory information. For example, intermediate drivers that
       modify packet data can use this flag to determine if data should be copied. Miniport drivers can use
       the flag to determine how to free the memory that is associated with a VM queue when a queue is
       deleted.</p>
</dd>

### -param <a id="NDIS_RECEIVE_FLAGS_MORE_NBLS"></a><a id="ndis_receive_flags_more_nbls"></a>NDIS_RECEIVE_FLAGS_MORE_NBLS

<dd>
<p>Reserved.</p>
</dd>
</dl>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p><i>ProtocolReceiveNetBufferLists</i> is a required function for protocol drivers. NDIS calls 
    <i>ProtocolReceiveNetBufferLists</i> after a bound miniport driver calls the 
    <a href="https://msdn.microsoft.com/b87dba3e-c18f-4ea2-8bd5-ec3cdafc534b">
    NdisMIndicateReceiveNetBufferLists</a> function. A call to 
    <i>ProtocolReceiveNetBufferLists</i> can also occur as a result of a loopback.</p>

<p>If the <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag in the 
    <i>ReceiveFlags</i> parameter is not set, the protocol driver retains ownership of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures until it calls
    the 
    <a href="https://msdn.microsoft.com/1a45bc5c-cdc1-46d2-905b-3d5eea3645c1">
    NdisReturnNetBufferLists</a> function.</p>

<p>If NDIS sets the <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag the protocol driver cannot retain the
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure and associated resources. The set <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag indicates
    that an underlying driver is running low on receive resources. In this case, the 
    <i>ProtocolReceiveNetBufferLists</i> function should copy the received data into protocol-allocated
    storage and return as quickly as possible.</p>

<p>On a multiprocessor system, this function can execute concurrently on more than one processor. Apply
    protection (for example, use spin locks) to critical data structures that are accessed by 
    <i>ProtocolReceiveNetBufferLists</i>.</p>

<p>NDIS calls 
    <i>ProtocolReceiveNetBufferLists</i> at IRQL&lt;= DISPATCH_LEVEL.</p>

<p>To define a <i>ProtocolReceiveNetBufferLists</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>ProtocolReceiveNetBufferLists</i> function that is named "MyReceiveNetBufferLists", use the <b>PROTOCOL_RECEIVE_NET_BUFFER_LISTS</b> type as shown in this code example:</p>

<p>Then, implement your function as follows:</p>

<p>The <b>PROTOCOL_RECEIVE_NET_BUFFER_LISTS</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_RECEIVE_NET_BUFFER_LISTS</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. </p>

<p><i>ProtocolReceiveNetBufferLists</i> is a required function for protocol drivers. NDIS calls 
    <i>ProtocolReceiveNetBufferLists</i> after a bound miniport driver calls the 
    <a href="https://msdn.microsoft.com/b87dba3e-c18f-4ea2-8bd5-ec3cdafc534b">
    NdisMIndicateReceiveNetBufferLists</a> function. A call to 
    <i>ProtocolReceiveNetBufferLists</i> can also occur as a result of a loopback.</p>

<p>If the <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag in the 
    <i>ReceiveFlags</i> parameter is not set, the protocol driver retains ownership of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures until it calls
    the 
    <a href="https://msdn.microsoft.com/1a45bc5c-cdc1-46d2-905b-3d5eea3645c1">
    NdisReturnNetBufferLists</a> function.</p>

<p>If NDIS sets the <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag the protocol driver cannot retain the
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure and associated resources. The set <b>NDIS_RECEIVE_FLAGS_RESOURCES</b> flag indicates
    that an underlying driver is running low on receive resources. In this case, the 
    <i>ProtocolReceiveNetBufferLists</i> function should copy the received data into protocol-allocated
    storage and return as quickly as possible.</p>

<p>On a multiprocessor system, this function can execute concurrently on more than one processor. Apply
    protection (for example, use spin locks) to critical data structures that are accessed by 
    <i>ProtocolReceiveNetBufferLists</i>.</p>

<p>NDIS calls 
    <i>ProtocolReceiveNetBufferLists</i> at IRQL&lt;= DISPATCH_LEVEL.</p>

<p>To define a <i>ProtocolReceiveNetBufferLists</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>ProtocolReceiveNetBufferLists</i> function that is named "MyReceiveNetBufferLists", use the <b>PROTOCOL_RECEIVE_NET_BUFFER_LISTS</b> type as shown in this code example:</p>

<p>Then, implement your function as follows:</p>

<p>The <b>PROTOCOL_RECEIVE_NET_BUFFER_LISTS</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_RECEIVE_NET_BUFFER_LISTS</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
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
<a href="https://msdn.microsoft.com/0f33ae87-164e-40dc-a915-28211a0d74b7">
   MiniportReturnNetBufferLists</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567211">NDIS_RECEIVE_QUEUE_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/b87dba3e-c18f-4ea2-8bd5-ec3cdafc534b">
   NdisMIndicateReceiveNetBufferLists</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564534">NdisReturnNetBufferLists</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_RECEIVE_NET_BUFFER_LISTS callback function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
