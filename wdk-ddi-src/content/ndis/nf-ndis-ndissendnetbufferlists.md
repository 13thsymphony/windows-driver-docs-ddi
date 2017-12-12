---
UID: NF.ndis.NdisSendNetBufferLists
title: NdisSendNetBufferLists function
author: windows-driver-content
description: Protocol drivers call the NdisSendNetBufferLists function to send network data that is contained in a list of NET_BUFFER_LIST structures.
old-location: netvista\ndissendnetbufferlists.htm
old-project: netvista
ms.assetid: f615acc4-7e3e-4390-8a6a-e68663fcc162
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisSendNetBufferLists
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
req.alt-api: NdisSendNetBufferLists
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_SendRcv_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <=DISPATCH_LEVEL
---

# NdisSendNetBufferLists function



## -description
Protocol drivers call the 
  <b>NdisSendNetBufferLists</b> function to send network data that is contained in a list of 
  <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures.



## -syntax

````
VOID NdisSendNetBufferLists(
  _In_ NDIS_HANDLE      NdisBindingHandle,
  _In_ PNET_BUFFER_LIST NetBufferLists,
  _In_ NDIS_PORT_NUMBER PortNumber,
  _In_ ULONG            SendFlags
);
````


## -parameters

### -param NdisBindingHandle [in]

A handle that identifies the target adapter. A previous call to 
     <a href="netvista.ndisopenadapterex">NdisOpenAdapterEx</a> returned this
     handle.


### -param NetBufferLists [in]

A pointer to a linked list of 
     <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures. Each
     NET_BUFFER_LIST structure describes a list of 
     <a href="netvista.net_buffer">NET_BUFFER</a> structures.


### -param PortNumber [in]

A port number that identifies a miniport adapter port. The default port number of a miniport
     adapter is zero. Protocol drivers that do not use miniport adapter ports should specify the default
     port.


### -param SendFlags [in]

Flags that define attributes for the send operation. The flags can be combined with an OR
     operation. To clear all the flags, set this member to zero. This function supports the following flags:
     




### -param NDIS_SEND_FLAGS_DISPATCH_LEVEL

Specifies that the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
       <a href="netvista.dispatch_irql_tracking">Dispatch IRQL Tracking</a>.


### -param NDIS_SEND_FLAGS_CHECK_FOR_LOOPBACK

Specifies that NDIS should check for loopback. By default, NDIS does not loop back data to the
       driver that submitted the send request. An overlying driver can override this behavior by setting this
       flag. When this flag is set, NDIS identifies all the NET_BUFFER structures that contain data that
       matches the receive criteria for the binding. NDIS indicates NET_BUFFER structures that match the
       criteria to the overlying driver. This flag has no affect on checking for loopback, or looping back,
       on other bindings.

</dd>
</dl>

## -returns
None


## -remarks
After a protocol driver calls 
    <b>NdisSendNetBufferLists</b>, NDIS submits the 
    <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures to an underlying
    driver's 
    <a href="..\ndis\nc-ndis-miniport_send_net_buffer_lists.md">
    MiniportSendNetBufferLists</a> function.

The protocol driver must allocate each NET_BUFFER_LIST structure from a pool by calling one of the
    following functions:


<a href="netvista.ndisallocatenetbufferlist">NdisAllocateNetBufferList</a>



<a href="netvista.ndisallocatenetbufferandnetbufferlist">
       NdisAllocateNetBufferAndNetBufferList</a>



<a href="netvista.ndisallocateclonenetbufferlist">
       NdisAllocateCloneNetBufferList</a>


The protocol driver can preallocate NET_BUFFER_LIST structures--for example, in its 
    <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine. Alternatively, the driver,
    can allocate the structures just prior to calling 
    <b>NdisSendNetBufferLists</b> and then free them when the send operation is complete. When NDIS returns a
    NET_BUFFER_LIST structure to 
    <a href="..\ndis\nc-ndis-protocol_send_net_buffer_lists_complete.md">
    ProtocolSendNetBufferListsComplete</a>, the miniport driver can prepare the NET_BUFFER_LIST structure
    and any associated resources for reuse. Reusing the NET_BUFFER_LIST structures can yield better
    performance than returning the structures to a pool and then reallocating them for another send
    operation.

A protocol driver must set the 
    <b>SourceHandle</b> member of each NET_BUFFER_LIST structure to the same value that it passes to the 
    <i>NdisBindingHandle</i> parameter. The binding handle provides the information that
    NDIS requires to return the NET_BUFFER_LIST structure to the protocol driver after the underlying
    miniport driver calls 
    <a href="netvista.ndismsendnetbufferlistscomplete">
    NdisMSendNetBufferListsComplete</a>.

Before calling 
    <b>NdisSendNetBufferLists</b>, a protocol driver can set information that accompanies the send request
    with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro . The
    underlying driver can retrieve this information with the NET_BUFFER_LIST_INFO macro.

Before a protocol driver calls 
    <b>NdisSendNetBufferLists</b> with a list of NET_BUFFER_LIST structures, the protocol driver must ensure
    that the NET_BUFFER_LIST structures are set up in the order that the network data should be sent over the
    wire.

As soon as a protocol driver calls 
    <b>NdisSendNetBufferLists</b>, it relinquishes ownership of the NET_BUFFER_LIST structures and all
    associated resources. NDIS calls the 
    <i>ProtocolSendNetBufferListsComplete</i> function to return the structures and data
    to the protocol driver. NDIS can collect the structures and data from multiple send requests into a
    single linked list of NET_BUFFER_LIST structures before it passes the list to 
    <i>ProtocolSendNetBufferListsComplete.</i>

Until NDIS calls 
    <i>ProtocolSendNetBufferListsComplete</i>, the current status of a
    protocol-driver-initiated send is not available to the protocol driver. A protocol driver temporarily
    releases ownership of all resources that it allocated for a send request when it calls 
    <b>NdisSendNetBufferLists</b>. A protocol driver should 
    <i>never</i> attempt to examine the NET_BUFFER_LIST structures or any associated data
    after calling 
    <b>NdisSendNetBufferLists</b>.


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
&lt;=DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.ndis_irql_sendrcv_function">Irql_SendRcv_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a>
</dt>
<dt>
<a href="netvista.ndisallocateclonenetbufferlist">
   NdisAllocateCloneNetBufferList</a>
</dt>
<dt>
<a href="netvista.ndisallocatenetbufferlist">NdisAllocateNetBufferList</a>
</dt>
<dt>
<a href="netvista.ndisallocatenetbufferandnetbufferlist">
   NdisAllocateNetBufferAndNetBufferList</a>
</dt>
<dt>
<a href="netvista.ndismallocateport">NdisMAllocatePort</a>
</dt>
<dt>
<a href="netvista.ndismsendnetbufferlistscomplete">
   NdisMSendNetBufferListsComplete</a>
</dt>
<dt>
<a href="netvista.ndisopenadapterex">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_send_net_buffer_lists.md">MiniportSendNetBufferLists</a>
</dt>
<dt>
<a href="netvista.net_buffer">NET_BUFFER</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_send_net_buffer_lists_complete.md">
   ProtocolSendNetBufferListsComplete</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisSendNetBufferLists function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

