---
UID: NF.ndis.NdisFSendNetBufferListsComplete
title: NdisFSendNetBufferListsComplete function
author: windows-driver-content
description: Filter drivers call the NdisFSendNetBufferListsComplete function to return a linked list of NET_BUFFER_LIST structures to an overlying driver and to return the final status of a send request.
old-location: netvista\ndisfsendnetbufferlistscomplete.htm
old-project: netvista
ms.assetid: 5a9008eb-86ad-4e3c-85a2-c8fd1b8fb4cb
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisFSendNetBufferListsComplete
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
req.alt-api: NdisFSendNetBufferListsComplete
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Filter_Driver_Function
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

# NdisFSendNetBufferListsComplete function



## -description
Filter drivers call the 
  <b>NdisFSendNetBufferListsComplete</b> function to return a linked list of 
  <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures to an overlying
  driver and to return the final status of a send request.



## -syntax

````
VOID NdisFSendNetBufferListsComplete(
  _In_ NDIS_HANDLE      NdisFilterHandle,
  _In_ PNET_BUFFER_LIST NetBufferLists,
  _In_ ULONG            SendCompleteFlags
);
````


## -parameters

### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


### -param NetBufferLists [in]

A pointer to a linked list of <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures. The filter driver received the
     <b>NET_BUFFER_LIST</b> structures in previous calls to the 
     <a href="..\ndis\nc-ndis-filter_send_net_buffer_lists.md">
     FilterSendNetBufferLists</a> function.


### -param SendCompleteFlags [in]

NDIS flags that can be combined with an OR operation. To clear all the flags, set this member to zero. This function supports the following flags:




### -param NDIS_SEND_COMPLETE_FLAGS_DISPATCH_LEVEL

Specifies that the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
        <a href="netvista.dispatch_irql_tracking">Dispatch IRQL Tracking</a>.


### -param NDIS_SEND_COMPLETE_FLAGS_SWITCH_SINGLE_SOURCE

If this flag is set, all packets in a linked list of <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures originated from the same Hyper-V extensible switch source port.

For more information, see <a href="netvista.hyper_v_extensible_switch_send_and_receive_flags">Hyper-V Extensible Switch Send and Receive Flags</a>.

<div class="alert"><b>Note</b>  If each packet in the linked list of <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures uses the same source port, the extension should set the <b>NDIS_SEND_FLAGS_SWITCH_SINGLE_SOURCE</b> flag in the <i>SendFlags</i> parameter of <a href="netvista.ndisfsendnetbufferlists">NdisFSendNetBufferLists</a> when it sends the request.</div>
<div> </div>
<div class="alert"><b>Note</b>  This flag is available in NDIS 6.30 and later.</div>
<div> </div>
</dd>
</dl>

## -returns
None


## -remarks
A filter driver calls the 
    <b>NdisFSendNetBufferListsComplete</b> function to complete send requests that NDIS made to the driver's 
    <a href="..\ndis\nc-ndis-filter_send_net_buffer_lists.md">
    FilterSendNetBufferLists</a> function. The filter driver specifies a linked list of 
    <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures that are
    associated with the completed send requests. While the status of the send requests is pending, the filter
    driver retains ownership of the <b>NET_BUFFER_LIST</b> structures and all the resources that are associated with
    the <b>NET_BUFFER_LIST</b> structures.

The filter driver can complete send requests in any order. For example, the filter driver could
    concatenate the <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure lists from multiple 
    <a href="..\ndis\nc-ndis-filter_send_net_buffer_lists.md">FilterSendNetBufferLists</a> calls or split up a list from a 
    <i>FilterSendNetBufferLists</i> call. However, the filter driver must not modify the list of 
    <a href="netvista.net_buffer">NET_BUFFER</a> structures that are associated with a
    <b>NET_BUFFER_LIST</b> structure.


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
<a href="devtest.ndis_irql_filter_driver_function">Irql_Filter_Driver_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_send_net_buffer_lists.md">FilterSendNetBufferLists</a>
</dt>
<dt>
<a href="netvista.net_buffer">NET_BUFFER</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFSendNetBufferListsComplete function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

