---
UID: NF.ndis.NdisMSendNetBufferListsComplete
title: NdisMSendNetBufferListsComplete function
author: windows-driver-content
description: Miniport drivers call the NdisMSendNetBufferListsComplete function to return a linked list of NET_BUFFER_LIST structures to an overlying driver and to return the final status of a send request.
old-location: netvista\ndismsendnetbufferlistscomplete.htm
old-project: netvista
ms.assetid: 33890582-5eba-4cc1-a0d9-ec07f18da453
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisMSendNetBufferListsComplete
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
req.alt-api: NdisMSendNetBufferListsComplete
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_SendRcv_Function, NdisTimedDataHang, NdisTimedDataSend
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

# NdisMSendNetBufferListsComplete function



## -description
Miniport drivers call the 
  <b>NdisMSendNetBufferListsComplete</b> function to return a linked list of 
  <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures to an overlying
  driver and to return the final status of a send request.



## -syntax

````
VOID NdisMSendNetBufferListsComplete(
  _In_ NDIS_HANDLE      MiniportAdapterHandle,
  _In_ PNET_BUFFER_LIST NetBufferLists,
  _In_ ULONG            SendCompleteFlags
);
````


## -parameters

### -param MiniportAdapterHandle [in]

The miniport handle that NDIS passed to the 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">
     MiniportInitializeEx</a> function.


### -param NetBufferLists [in]

A pointer to a linked list of NET_BUFFER_LIST structures. The miniport driver received the
     NET_BUFFER_LIST structures in previous calls to its 
     <a href="..\ndis\nc-ndis-miniport_send_net_buffer_lists.md">
     MiniportSendNetBufferLists</a> function.


### -param SendCompleteFlags [in]

NDIS flags that can be combined with an OR operation. To clear all the flags, set this member to
     zero. This function supports the NDIS_SEND_COMPLETE_FLAGS_DISPATCH_LEVEL flag which; if set, indicates
     that the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
     <a href="netvista.dispatch_irql_tracking">Dispatch IRQL Tracking</a>.


## -returns
None


## -remarks
A miniport driver calls 
    <b>NdisMSendNetBufferListsComplete</b> to complete send requests that NDIS made to the driver's 
    <a href="..\ndis\nc-ndis-miniport_send_net_buffer_lists.md">
    MiniportSendNetBufferLists</a> function. The miniport driver specifies a linked list of 
    <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures that are
    associated with the completed send requests. While the status of the send requests is pending, the
    miniport driver retains ownership of the NET_BUFFER_LIST structures and all the protocol-allocated
    resources that are associated with the NET_BUFFER_LIST structures.

After a miniport driver calls 
    <b>NdisMSendNetBufferListsComplete</b>, NDIS calls the 
    <a href="..\ndis\nc-ndis-protocol_send_net_buffer_lists_complete.md">
    ProtocolSendNetBufferListsComplete</a> function of the driver that called the 
    <a href="netvista.ndissendnetbufferlists">NdisSendNetBufferLists</a> function to
    initiate the send request.

The miniport driver can complete send requests in any order. For example, the miniport driver could
    concatenate the NET_BUFFER_LIST structure lists from multiple 
    <i>MiniportSendNetBufferLists</i> calls or split up a list from a 
    <i>MiniportSendNetBufferLists</i> call. However, the miniport driver must not modify the list of 
    <a href="netvista.net_buffer">NET_BUFFER</a> structures that are associated with a
    NET_BUFFER_LIST structure.

The miniport driver must set one of the following status codes in the 
    <b>Status</b> member of each NET_BUFFER_LIST structure that the 
    <i>NetBufferLists</i> parameter specifies:



All the network data that the NET_BUFFER_LIST structure and the associated NET_BUFFER structures
      describe was successfully processed for transmission. For example, the miniport driver copied the data
      to a queue or the data has already been transmitted.

The size of the data in some NET_BUFFER structures associated with this NET_BUFFER_LIST structure
      was too large for the underlying NIC.

The send request for this NET_BUFFER_LIST structure failed due to insufficient resources.

The miniport adapter is in the 
      <i>Paused</i> state, as described on the reference page for the 
      <a href="..\ndis\nc-ndis-miniport_pause.md">MiniportPause</a> function.

NDIS called the 
      <a href="..\ndis\nc-ndis-miniport_cancel_send.md">MiniportCancelSend</a> function to
      cancel the send operation for this NET_BUFFER_LIST structure.

The miniport driver aborted the send request due to a reset.

The miniport driver failed the send request because of some reason other than those previously
      described. For example, the miniport driver can fail the send request due to a hardware failure.

A miniport driver's call to 
    <b>NdisMSendNetBufferListsComplete</b> does not necessarily mean that the data for a send request has been
    transmitted over the network. The data might be queued in the NIC hardware.


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
&lt;= DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.ndis_irql_sendrcv_function">Irql_SendRcv_Function</a>, <a href="devtest.ndis_ndistimeddatahang">NdisTimedDataHang</a>, <a href="devtest.ndis_ndistimeddatasend">NdisTimedDataSend</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_cancel_send.md">MiniportCancelSend</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_send_net_buffer_lists.md">MiniportSendNetBufferLists</a>
</dt>
<dt>
<a href="netvista.ndissendnetbufferlists">NdisSendNetBufferLists</a>
</dt>
<dt>
<a href="netvista.net_buffer">NET_BUFFER</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMSendNetBufferListsComplete function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

