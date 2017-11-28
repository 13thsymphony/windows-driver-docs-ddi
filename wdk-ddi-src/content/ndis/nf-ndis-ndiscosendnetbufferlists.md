---
UID: NF.ndis.NdisCoSendNetBufferLists
title: NdisCoSendNetBufferLists
author: windows-driver-content
description: The NdisCoSendNetBufferLists function sends network data that is contained in a specified list of NET_BUFFER_LIST structures.
old-location: netvista\ndiscosendnetbufferlists.htm
old-project: netvista
ms.assetid: 8284fdd4-26de-4622-b164-f33aee1d8742
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: NdisCoSendNetBufferLists
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 drivers in Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisCoSendNetBufferLists
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Connection_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.iface: 
---

# NdisCoSendNetBufferLists function



## -description
<p>The 
  <b>NdisCoSendNetBufferLists</b> function sends network data that is contained in a specified list of 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures.</p>


## -syntax

````
VOID NdisCoSendNetBufferLists(
  _In_ NDIS_HANDLE      NdisVcHandle,
  _In_ PNET_BUFFER_LIST NetBufferLists,
  _In_ ULONG            SendFlags
);
````


## -parameters
<dl>

### -param <i>NdisVcHandle</i> [in]

<dd>
<p>A handle to a virtual connection (VC) that identifies the target of the send request.</p>
</dd>

### -param <i>NetBufferLists</i> [in]

<dd>
<p>A pointer to a linked list of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures. Each
     NET_BUFFER_LIST structure describes a list of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures.</p>
</dd>

### -param <i>SendFlags</i> [in]

<dd>
<p>Flags that define attributes for the send operation. The flags can be combined with a bitwise OR
     operation. To clear all of the flags, set this parameter to zero. 
     <b>NdisCoSendNetBufferLists</b> supports the following flags:
     </p>
<p></p>
<dl>

### -param <a id="NDIS_SEND_FLAGS_DISPATCH_LEVEL"></a><a id="ndis_send_flags_dispatch_level"></a>NDIS_SEND_FLAGS_DISPATCH_LEVEL

<dd>
<p>The current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
       <a href="NULL">Dispatch IRQL Tracking</a>.</p>
</dd>

### -param <a id="NDIS_SEND_FLAGS_CHECK_FOR_LOOPBACK"></a><a id="ndis_send_flags_check_for_loopback"></a>NDIS_SEND_FLAGS_CHECK_FOR_LOOPBACK

<dd>
<p>NDIS should check for loopback. By default, NDIS does not loop back data to the driver that
       submitted the send request. An overlying driver can override this behavior by setting
       NDIS_SEND_FLAGS_CHECK_FOR_LOOPBACK. When this flag is set, NDIS identifies all of the NET_BUFFER
       structures that contain data that matches the receive criteria for the binding. NDIS indicates
       NET_BUFFER structures that match the criteria to the overlying driver. This flag does not affect
       checking for loopback, or looping back, on other bindings.</p>
</dd>
</dl>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>After a CoNDIS protocol driver calls 
    <b>NdisCoSendNetBufferLists</b>, NDIS submits the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures that the 
    <i>NetBufferLists</i> parameter specifies to an underlying driver's 
    <a href="..\ndis\nc-ndis-miniport-co-send-net-buffer-lists.md">
    MiniportCoSendNetBufferLists</a> function.</p>

<p>The protocol driver must allocate each NET_BUFFER_LIST structure from a pool by calling one of the
    following functions:</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561609">NdisAllocateNetBufferList</a>
</p>

<p>
<a href="..\ndis\nf-ndis-ndisallocatenetbufferandnetbufferlist.md">
       NdisAllocateNetBufferAndNetBufferList</a>
</p>

<p>
<a href="..\ndis\nf-ndis-ndisallocateclonenetbufferlist.md">
       NdisAllocateCloneNetBufferList</a>
</p>

<p>The protocol driver can preallocate NET_BUFFER_LIST structures--for example, in its 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine. Alternatively, the protocol
    driver can allocate the structures immediately prior to calling 
    <b>NdisCoSendNetBufferLists</b> and then can free them when the send operation is complete. When NDIS
    returns a NET_BUFFER_LIST structure to the 
    <a href="..\ndis\nc-ndis-protocol-co-send-net-buffer-lists-complete.md">
    ProtocolCoSendNetBufferListsComplete</a> function, the protocol driver can prepare the NET_BUFFER_LIST
    structure and any associated resources for reuse. If you reuse the NET_BUFFER_LIST structures, you can
    get better performance than returning the structures to a pool and then reallocating them for another
    send operation.</p>

<p>A protocol driver must set the 
    <b>SourceHandle</b> member of each 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure to the same value
    that it passes at the 
    <i>NdisVcHandle</i> parameter. The source handle provides the information that NDIS requires to return the
    NET_BUFFER_LIST structure to the protocol driver after the underlying miniport driver calls the 
    <a href="..\ndis\nf-ndis-ndismcosendnetbufferlistscomplete.md">
    NdisMCoSendNetBufferListsComplete</a> function.</p>

<p>Before a protocol driver calls 
    <b>NdisCoSendNetBufferLists</b>, the driver can set information that accompanies the send request with
    the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro. The
    underlying driver can retrieve this information with the NET_BUFFER_LIST_INFO macro.</p>

<p>Before a protocol driver calls 
    <b>NdisCoSendNetBufferLists</b> with a list of NET_BUFFER_LIST structures, the protocol driver must ensure
    that the NET_BUFFER_LIST structures are set up in the order that the network data should be sent.</p>

<p>As soon as a protocol driver calls 
    <b>NdisCoSendNetBufferLists</b>, it no longer owns the NET_BUFFER_LIST structures and all of the
    associated resources. NDIS calls the 
    <i>ProtocolCoSendNetBufferListsComplete</i> function to return the structures and data to the protocol
    driver. NDIS can collect the structures and data from multiple send requests into a single linked list of
    NET_BUFFER_LIST structures before it passes the list to 
    <i>ProtocolCoSendNetBufferListsComplete</i>.</p>

<p>Until NDIS calls 
    <i>ProtocolCoSendNetBufferListsComplete</i>, the current status of a protocol driver-initiated send is
    not available to the protocol driver. A protocol driver temporarily releases ownership of all of the
    resources that it allocated for a send request when it calls 
    <b>NdisCoSendNetBufferLists</b>. A protocol driver should never attempt to examine the NET_BUFFER_LIST
    structures or any associated data after the driver calls 
    <b>NdisCoSendNetBufferLists</b>.</p>

<p>After a CoNDIS protocol driver calls 
    <b>NdisCoSendNetBufferLists</b>, NDIS submits the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures that the 
    <i>NetBufferLists</i> parameter specifies to an underlying driver's 
    <a href="..\ndis\nc-ndis-miniport-co-send-net-buffer-lists.md">
    MiniportCoSendNetBufferLists</a> function.</p>

<p>The protocol driver must allocate each NET_BUFFER_LIST structure from a pool by calling one of the
    following functions:</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561609">NdisAllocateNetBufferList</a>
</p>

<p>
<a href="..\ndis\nf-ndis-ndisallocatenetbufferandnetbufferlist.md">
       NdisAllocateNetBufferAndNetBufferList</a>
</p>

<p>
<a href="..\ndis\nf-ndis-ndisallocateclonenetbufferlist.md">
       NdisAllocateCloneNetBufferList</a>
</p>

<p>The protocol driver can preallocate NET_BUFFER_LIST structures--for example, in its 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine. Alternatively, the protocol
    driver can allocate the structures immediately prior to calling 
    <b>NdisCoSendNetBufferLists</b> and then can free them when the send operation is complete. When NDIS
    returns a NET_BUFFER_LIST structure to the 
    <a href="..\ndis\nc-ndis-protocol-co-send-net-buffer-lists-complete.md">
    ProtocolCoSendNetBufferListsComplete</a> function, the protocol driver can prepare the NET_BUFFER_LIST
    structure and any associated resources for reuse. If you reuse the NET_BUFFER_LIST structures, you can
    get better performance than returning the structures to a pool and then reallocating them for another
    send operation.</p>

<p>A protocol driver must set the 
    <b>SourceHandle</b> member of each 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure to the same value
    that it passes at the 
    <i>NdisVcHandle</i> parameter. The source handle provides the information that NDIS requires to return the
    NET_BUFFER_LIST structure to the protocol driver after the underlying miniport driver calls the 
    <a href="..\ndis\nf-ndis-ndismcosendnetbufferlistscomplete.md">
    NdisMCoSendNetBufferListsComplete</a> function.</p>

<p>Before a protocol driver calls 
    <b>NdisCoSendNetBufferLists</b>, the driver can set information that accompanies the send request with
    the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro. The
    underlying driver can retrieve this information with the NET_BUFFER_LIST_INFO macro.</p>

<p>Before a protocol driver calls 
    <b>NdisCoSendNetBufferLists</b> with a list of NET_BUFFER_LIST structures, the protocol driver must ensure
    that the NET_BUFFER_LIST structures are set up in the order that the network data should be sent.</p>

<p>As soon as a protocol driver calls 
    <b>NdisCoSendNetBufferLists</b>, it no longer owns the NET_BUFFER_LIST structures and all of the
    associated resources. NDIS calls the 
    <i>ProtocolCoSendNetBufferListsComplete</i> function to return the structures and data to the protocol
    driver. NDIS can collect the structures and data from multiple send requests into a single linked list of
    NET_BUFFER_LIST structures before it passes the list to 
    <i>ProtocolCoSendNetBufferListsComplete</i>.</p>

<p>Until NDIS calls 
    <i>ProtocolCoSendNetBufferListsComplete</i>, the current status of a protocol driver-initiated send is
    not available to the protocol driver. A protocol driver temporarily releases ownership of all of the
    resources that it allocated for a send request when it calls 
    <b>NdisCoSendNetBufferLists</b>. A protocol driver should never attempt to examine the NET_BUFFER_LIST
    structures or any associated data after the driver calls 
    <b>NdisCoSendNetBufferLists</b>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported for NDIS 6.0 drivers in Windows Vista.</p>
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
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;=DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547924">Irql_Connection_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-co-send-net-buffer-lists.md">
   MiniportCoSendNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisallocateclonenetbufferlist.md">
   NdisAllocateCloneNetBufferList</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561609">NdisAllocateNetBufferList</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisallocatenetbufferandnetbufferlist.md">
   NdisAllocateNetBufferAndNetBufferList</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismcosendnetbufferlistscomplete.md">
   NdisMCoSendNetBufferListsComplete</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol-co-send-net-buffer-lists-complete.md">
   ProtocolCoSendNetBufferListsComplete</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCoSendNetBufferLists function%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
