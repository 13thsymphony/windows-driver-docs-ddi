---
UID: NF:ndis.NdisGetNetBufferListProtocolId
title: NdisGetNetBufferListProtocolId function
author: windows-driver-content
description: The NdisGetNetBufferListProtocolId function retrieves the protocol identifier from the NetBufferListInfo member of a NET_BUFFER_LIST structure.
old-location: netvista\ndisgetnetbufferlistprotocolid.htm
old-project: netvista
ms.assetid: a90b1318-ce21-4483-b253-767674fe0a2f
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: NdisGetNetBufferListProtocolId
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
req.alt-api: NdisGetNetBufferListProtocolId
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisGetNetBufferListProtocolId function



## -description
The 
  <b>NdisGetNetBufferListProtocolId</b> function retrieves the protocol identifier from the 
  <b>NetBufferListInfo</b> member of a 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.



## -syntax

````
UCHAR NdisGetNetBufferListProtocolId(
  _In_ PNET_BUFFER_LIST NetBufferList
);
````


## -parameters

### -param NetBufferList [in]

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.


## -returns
<b>NdisGetNetBufferListProtocolId</b> returns a protocol identifier as one of the following
     values:
<dl>
<dt><b>NDIS_PROTOCOL_ID_DEFAULT</b></dt>
</dl>A default protocol driver identifier.
<dl>
<dt><b>NDIS_PROTOCOL_ID_TCP_IP</b></dt>
</dl>The TCP/IP protocol identifier.
<dl>
<dt><b>NDIS_PROTOCOL_ID_IPX</b></dt>
</dl>The IPX protocol identifier.
<dl>
<dt><b>NDIS_PROTOCOL_ID_NBF</b></dt>
</dl>The NetBEUI protocol identifier.

 


## -remarks
NDIS drivers can call the 
    <b>NdisGetNetBufferListProtocolId</b> function to determine the type of protocol driver that created a 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. For example,
    miniport drivers that support TCP chimney offload can verify that a NET_BUFFER_LIST structure comes from
    a TCP protocol.

Protocol drivers that create NET_BUFFER_LIST structures should set the protocol identifier by calling
    the 
    <a href="https://msdn.microsoft.com/e143c914-cfb0-4c06-9da7-a2f5ef09afe2">
    NdisSetNetBufferListProtocolId</a> macro or by associating an identifier with a NET_BUFFER_LIST
    pool.


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
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/e143c914-cfb0-4c06-9da7-a2f5ef09afe2">
   NdisSetNetBufferListProtocolId</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGetNetBufferListProtocolId function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

