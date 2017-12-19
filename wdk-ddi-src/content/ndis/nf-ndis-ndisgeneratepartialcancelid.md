---
UID: NF.ndis.NdisGeneratePartialCancelId
title: NdisGeneratePartialCancelId function
author: windows-driver-content
description: The NdisGeneratePartialCancelId function returns a value that the calling driver must use as the high-order byte of a cancellation ID.
old-location: netvista\ndisgeneratepartialcancelid.htm
old-project: NetVista
ms.assetid: a26e9602-058b-401b-85be-9d80e4ef213b
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisGeneratePartialCancelId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisGeneratePartialCancelId   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisGeneratePartialCancelId   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisGeneratePartialCancelId
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Miscellaneous_Function
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

# NdisGeneratePartialCancelId function



## -description
The
  <b>NdisGeneratePartialCancelId</b> function returns a value that the calling driver must use as the
  high-order byte of a cancellation ID.



## -syntax

````
UCHAR NdisGeneratePartialCancelId(void);
````


## -parameters


## -returns
<b>NdisGeneratePartialCancelId</b> returns a value that the calling driver uses as the high-order byte of
     a cancellation ID.

<b>NdisGeneratePartialCancelId</b> returns a value that the calling driver uses as the high-order byte of
     a cancellation ID.

<b>NdisGeneratePartialCancelId</b> returns a value that the calling driver uses as the high-order byte of
     a cancellation ID.


## -remarks
Before marking send 
    <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures with cancellation
    IDs by calling the 
    <a href="netvista.ndis_set_net_buffer_list_cancel_id">
    NDIS_SET_NET_BUFFER_LIST_CANCEL_ID</a> macro, a driver should call 
    <b>NdisGeneratePartialCancelId</b> one or more times. 
    <b>NdisGeneratePartialCancelId</b> returns a value that the calling driver can use as the high-order byte
    of a cancellation ID. Prefixing a cancellation ID with the value returned by 
    <b>NdisGeneratePartialCancelId</b> ensures that the cancellation ID will not be a duplicate of a
    cancellation ID assigned by another driver in the local computer.

Typically, an overlying driver calls 
    <b>NdisGeneratePartialCancelId</b> one or more times during its initialization sequence and stores the
    returned value or values for later use. A protocol driver, for example, could call 
    <b>NdisGeneratePartialCancelId</b> once for each client (such as DHCP or ARC) that it supports. The
    protocol driver can call the 
    <a href="netvista.ndiscancelsendnetbufferlists">
    NdisCancelSendNetBufferLists</a> function later to cancel a send request. In this case, NDIS calls the
    cancel send function (for example, 
    <a href="..\ndis\nc-ndis-miniport_cancel_send.md">MiniportCancelSend</a>) of the
    underlying drivers.


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
Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/8dd3dae6-a867-421c-b1c3-65fd14c56deb">NdisGeneratePartialCancelId
   (NDIS 5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisGeneratePartialCancelId
   (NDIS 5.1)</b>) in Windows XP.

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
<a href="devtest.ndis_irql_miscellaneous_function">Irql_Miscellaneous_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_cancel_send.md">MiniportCancelSend</a>
</dt>
<dt>
<a href="netvista.ndiscancelsendnetbufferlists">NdisCancelSendNetBufferLists</a>
</dt>
<dt>
<a href="netvista.ndis_set_net_buffer_list_cancel_id">
   NDIS_SET_NET_BUFFER_LIST_CANCEL_ID</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisGeneratePartialCancelId function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

