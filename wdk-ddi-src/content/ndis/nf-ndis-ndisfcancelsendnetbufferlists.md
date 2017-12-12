---
UID: NF.ndis.NdisFCancelSendNetBufferLists
title: NdisFCancelSendNetBufferLists function
author: windows-driver-content
description: Filter drivers call the NdisFCancelSendNetBufferLists function to cancel the transmission of network data.
old-location: netvista\ndisfcancelsendnetbufferlists.htm
old-project: netvista
ms.assetid: 358b1aa9-4bfd-4bed-94f7-1b021c732a02
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisFCancelSendNetBufferLists
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
req.alt-api: NdisFCancelSendNetBufferLists
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

# NdisFCancelSendNetBufferLists function



## -description
Filter drivers call the 
  <b>NdisFCancelSendNetBufferLists</b> function to cancel the transmission of network data.



## -syntax

````
VOID NdisFCancelSendNetBufferLists(
  _In_ NDIS_HANDLE NdisFilterHandle,
  _In_ PVOID       CancelId
);
````


## -parameters

### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


### -param CancelId [in]

The cancellation identifier. This identifier specifies the network data for the transmission that
     is being canceled.


## -returns
None


## -remarks
A filter driver can cancel the send requests that it originates or pass on the cancellation requests
    from overlying drivers. To cancel a send request from an overlying driver, NDIS calls the filter drivers 
    <a href="netvista.filtercancelsendnetbufferlists">
    FilterCancelSendNetBufferLists</a> function.

A filter driver can call the 
    <a href="netvista.ndis_set_net_buffer_list_cancel_id">
    NDIS_SET_NET_BUFFER_LIST_CANCEL_ID</a> macro to mark NET_BUFFER_LIST structures that it originates and
    passes down to lower-level drivers for transmission. The NDIS_SET_NET_BUFFER_LIST_CANCEL_ID macro marks
    the specified packet with a cancellation identifier.

<b>NdisFCancelSendNetBufferLists</b> cancels the transmission of all data that is marked with the
    specified cancellation identifier.

NDIS returns canceled send data that the filter driver originated to the 
    <a href="..\ndis\nc-ndis-filter_send_net_buffer_lists_complete.md">
    FilterSendNetBufferListsComplete</a> function. The completion status of canceled requests is
    NDIS_STATUS_SEND_ABORTED.


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
<a href="netvista.filtercancelsendnetbufferlists">
   FilterCancelSendNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_send_net_buffer_lists_complete.md">
   FilterSendNetBufferListsComplete</a>
</dt>
<dt>
<a href="netvista.ndis_set_net_buffer_list_cancel_id">
   NDIS_SET_NET_BUFFER_LIST_CANCEL_ID</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFCancelSendNetBufferLists function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

