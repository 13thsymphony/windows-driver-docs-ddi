---
UID: NC.ndischimney.TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER
title: TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER
author: windows-driver-content
description: NDIS calls a protocol or intermediate driver's ProtocolTcpOffloadForwardComplete function to complete a forward operation that the driver previously initiated by calling the NdisOffloadTcpForward function.
old-location: netvista\protocoltcpoffloadforwardcomplete.htm
old-project: NetVista
ms.assetid: 02a11841-d98a-4c74-8922-458826e2911e
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _PD_BUFFER_VIRTUAL_SUBNET_INFO, PD_BUFFER_VIRTUAL_SUBNET_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProtocolTcpOffloadForwardComplete
req.alt-loc: Ndischimney.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER callback



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol or intermediate driver's 
  <i>ProtocolTcpOffloadForwardComplete</i> function to complete a forward operation that the driver previously
  initiated by calling the 
  <a href="netvista.ndisoffloadtcpdisconnect">
  NdisOffloadTcpForward</a> function.



## -prototype

````
TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER ProtocolTcpOffloadForwardComplete;

VOID ProtocolTcpOffloadForwardComplete(
  _In_ NDIS_HANDLE      ProtocolBindingContext,
  _In_ PNET_BUFFER_LIST NetBufferList
)
{ ... }
````


## -parameters

### -param ProtocolBindingContext [in]

A handle to a context area allocated by the protocol driver. The driver maintains the per binding
     context information in this context area. The driver supplied this handle to NDIS when the driver called
     the 
     <a href="netvista.ndisopenadapterex">NdisOpenAdapterEx</a> function.


### -param NetBufferList [in]

A pointer to a 
     <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure. This structure
     can be stand-alone or the first structure in a linked list of NET_BUFFER_LIST structures. The driver
     supplied this pointer as an input parameter in a previous call to the 
     <b>NdisOffloadTcpForward</b> function.


## -returns
None


## -remarks
In response to an underlying driver's or offload target's call to the 
    <b>NdisOffloadTcpForwardComplete</b> function, NDIS calls the overlying protocol driver's or intermediate
    driver's 
    <i>ProtocolTcpOffloadForwardComplete</i> function.

To propagate the completion of the forward operation to the overlying driver or host stack, the
    intermediate driver calls the 
    <b>NdisOffloadTcpForwardComplete</b> function, passing in the following:

A 
      <i>ProtocolBindingContext</i>, which is a handle that uniquely identifies the intermediate driver.

The PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <i>ProtocolTcpOffloadForwardComplete</i> function.

In response, NDIS calls the overlying driver's or host stack's 
    <i>ProtocolTcpOffloadForwardComplete</i> function, passing in a 
    <i>ProtocolBindingContext</i> handle and the PNET_BUFFER_LIST pointer supplied by the intermediate driver
    to the 
    <b>NdisOffloadTcpForwardComplete</b> function.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndischimney.h (include Ndischimney.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_forward_handler.md">MiniportTcpOffloadForward</a>
</dt>
<dt>
<a href="netvista.ndisoffloadtcpdisconnect">NdisOffloadTcpForward</a>
</dt>
<dt>
<a href="netvista.ndisopenadapterex">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_forward_complete.md">
   NdisTcpOffloadForwardComplete</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

