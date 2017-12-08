---
UID: NF.fwpsk.FwpsInjectTransportSendAsync0
title: FwpsInjectTransportSendAsync0 function
author: windows-driver-content
description: The FwpsInjectTransportSendAsync0 function injects packet data from the transport, datagram data, or ICMP error layers into the send data path.Note  FwpsInjectTransportSendAsync0 is the specific version of FwpsInjectTransportSendAsync used in Windows Vista and later. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information. For Windows 7, FwpsInjectTransportSendAsync1 is available.
old-location: netvista\fwpsinjecttransportsendasync0.htm
old-project: netvista
ms.assetid: 1298a825-16c4-49ab-b038-19247975ea46
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: FwpsInjectTransportSendAsync0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FwpsInjectTransportSendAsync0
req.alt-loc: fwpkclnt.lib,fwpkclnt.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# FwpsInjectTransportSendAsync0 function



## -description
The 
  <b>FwpsInjectTransportSendAsync0</b> function injects packet data from the transport, datagram data, or ICMP
  error layers into the send data path.


## -syntax

````
NTSTATUS NTAPI FwpsInjectTransportSendAsync0(
  _In_     HANDLE                      injectionHandle,
  _In_opt_ HANDLE                      injectionContext,
  _In_     UINT64                      endpointHandle,
  _In_     UINT32                      flags,
  _In_opt_ FWPS_TRANSPORT_SEND_PARAMS0 *sendArgs,
  _In_     ADDRESS_FAMILY              addressFamily,
  _In_     COMPARTMENT_ID              compartmentId,
  _Inout_  NET_BUFFER_LIST             *netBufferList,
  _In_     FWPS_INJECT_COMPLETE0       completionFn,
  _In_opt_ HANDLE                      completionContext
);
````


## -parameters

### -param injectionHandle [in]

An injection handle that was previously created by a call to the 
     <a href="netvista.fwpsinjectionhandlecreate0">
     FwpsInjectionHandleCreate0</a> function.

### -param injectionContext [in, optional]

An optional handle to the injection context. If specified, it can be obtained by calling the 
     <a href="netvista.fwpsquerypacketinjectionstate0">FwpsQueryPacketInjectionState0</a> function when the packet injection state 
     <a href="netvista.fwps_packet_injection_state">FWPS_PACKET_INJECTION_STATE</a> is
     <b>FWPS_PACKET_INJECTED_BY_SELF</b> or <b>FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF</b>.

### -param endpointHandle [in]

A handle that indicates the stack transport endpoint in the send data path into which the packet
     is to be injected. This endpoint handle is provided to a callout through the 
     <b>transportEndpointHandle</b> member of the 
     <a href="netvista.fwps_incoming_metadata_values0">
     FWPS_INCOMING_METADATA_VALUES0</a> structure that is passed to the callout driver's 
     <a href="netvista.classifyfn">classifyFn</a> callout function. Callout
     drivers should use the provided handle to inject cloned packets back into the data path as soon as
     possible, before the socket associated with the stack endpoint is closed and the handle becomes no
     longer valid.

### -param flags [in]

Reserved. Callout drivers must set this parameter to zero.

### -param sendArgs [in, optional]

A pointer to a 
     <a href="netvista.fwps_transport_send_params0">
     FWPS_TRANSPORT_SEND_PARAMS0</a> structure that specifies the properties of the current outbound
     packet. Can be <b>NULL</b> only if the net buffer list to be injected contains an IP header (for example, if
     the packet is sent via a raw socket).

### -param addressFamily [in]

One of the following address families:
     


### -param AF_INET

The IPv4 address family.

### -param AF_INET6

The IPv6 address family.
</dd>
</dl>

### -param compartmentId [in]

The identifier of the routing compartment into which the packet data is injected, specified as a 
     <a href="kernel.compartment_id">COMPARTMENT_ID</a> type. This identifier is provided
     to a callout through the 
     <b>compartmentId</b> member of the 
     <a href="netvista.fwps_incoming_metadata_values0">
     FWPS_INCOMING_METADATA_VALUES0</a> structure that is passed to the callout driver's 
     <a href="netvista.classifyfn">classifyFn</a> callout function. If the 
     <b>compartmentId</b> member is available to callouts, FWPS_METADATA_FIELD_COMPARTMENT_ID will be set in
     the 
     <b>currentMetadataValues</b> member. Otherwise, set this parameter to UNSPECIFIED_COMPARTMENT_ID.

### -param netBufferList [in, out]

A pointer to a 
     <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure that describes
     the packet data that is being injected. A callout driver allocates a <b>NET_BUFFER_LIST</b> structure to use to
     inject packet data by calling either the 
     <a href="netvista.fwpsallocateclonenetbufferlist0">
     FwpsAllocateCloneNetBufferList0</a> function or the 
     <a href="netvista.fwpsallocatenetbufferandnetbufferlist0">
     FwpsAllocateNetBufferAndNetBufferList0</a> function.

### -param completionFn [in]

A pointer to a 
     <a href="..\fwpsk\nc-fwpsk-fwps_inject_complete0.md">completionFn</a> callout function provided by
     the callout driver. The filter engine calls this function after the packet data, described by the 
     <i>netBufferList</i> parameter, has been injected into the network stack.

### -param completionContext [in, optional]

A pointer to a callout driver-provided context that is passed to the callout function pointed to
     by the 
     <i>completionFn</i> parameter. This parameter is optional and can be <b>NULL</b>.

## -returns
The 
     <a href="netvista.fwpsinjectnetworksendasync0">FwpsInjectNetworkSendAsync0</a> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The packet data injection was initiated successfully. The filter engine will call the completion
       function after the filter engine has completed injecting the packet data into the network stack, or
       when an error occurred subsequently. In case of an error, the 
       <b>Status</b> member of the completed 
       <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure will indicate
       the reason for failure.
<dl>
<dt><b>STATUS_FWP_TCPIP_NOT_READY</b></dt>
</dl>The TCP/IP network stack is not ready to accept injection of packet data.
<dl>
<dt><b>STATUS_FWP_INJECT_HANDLE_CLOSING</b></dt>
</dl>The injection handle is being closed.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 

## -remarks
A callout driver calls the 
    <a href="netvista.fwpsinjectnetworksendasync0">FwpsInjectNetworkSendAsync0</a> function to inject packet data from the transport, datagram data, or
    ICMP error layers into the send data path. At these layers, the IP header might not yet be formed, and
    when IPsec policy is active, the packet data is not encrypted or signed. Therefore, this function is
    ideal to use for packet inspection in an IPsec-enabled environment.

This function can execute asynchronously.

If the return value is not STATUS_SUCCESS, the completion function will not be called. In this case,
    the net buffer list pointed to by 
    <i>netBufferList</i> needs to be freed by a call to 
    <a href="netvista.fwpsfreenetbufferlist0">FwpsFreeNetBufferList0</a> or 
    <a href="netvista.fwpsfreeclonenetbufferlist0">FwpsFreeCloneNetBufferList0</a>.

Callout drivers normally inject data into the network stack when they modify packet data. For more
    information about how a callout driver can modify packet data, see 
    <a href="netvista.callout_driver_operations">Callout Driver Operations</a>.

The injected packet can be indicated to the callout driver again. To prevent infinite looping, the
    driver should first call the 
    <a href="netvista.fwpsquerypacketinjectionstate0">FwpsQueryPacketInjectionState0</a> function before calling the 
    <a href="netvista.classifyfn">classifyFn</a> callout function, and permit
    packets that have the injection state 
    <a href="netvista.fwps_packet_injection_state">FWPS_PACKET_INJECTION_STATE</a> set to
    <b>FWPS_PACKET_INJECTED_BY_SELF</b> or <b>FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF</b>.

The 
    <i>endpointHandle</i> parameter, as well as members declared in the 
    <a href="netvista.fwps_transport_send_params0">
    FWPS_TRANSPORT_SEND_PARAMS0</a> structure pointed to by the 
    <i>sendArgs</i> parameter, are provided to callouts from the following network layers:


<dl>
<dd>
FWPS_LAYER_OUTBOUND_TRANSPORT_V4
</dd>
<dd>
FWPS_LAYER_OUTBOUND_TRANSPORT_V6
</dd>
<dd>
FWPS_LAYER_DATAGRAM_DATA_V4 (when outbound direction is specified with FWP_DIRECTION_OUTBOUND)
</dd>
<dd>
FWPS_LAYER_DATAGRAM_DATA_V6 (when outbound direction is specified with FWP_DIRECTION_OUTBOUND)
</dd>
<dd>
FWPS_LAYER_OUTBOUND_ICMP_ERROR_V4
</dd>
<dd>
FWPS_LAYER_OUTBOUND_ICMP_ERROR_V6
</dd>
</dl>


FWPS_LAYER_OUTBOUND_TRANSPORT_V4

FWPS_LAYER_OUTBOUND_TRANSPORT_V6

FWPS_LAYER_DATAGRAM_DATA_V4 (when outbound direction is specified with FWP_DIRECTION_OUTBOUND)

FWPS_LAYER_DATAGRAM_DATA_V6 (when outbound direction is specified with FWP_DIRECTION_OUTBOUND)

FWPS_LAYER_OUTBOUND_ICMP_ERROR_V4

FWPS_LAYER_OUTBOUND_ICMP_ERROR_V6

The datagram belongs to a raw socket if both of the following are true: <ul>
<li>The <b>currentMetadataValues</b> member of the <a href="netvista.fwps_incoming_metadata_values0">FWPS_INCOMING_METADATA_VALUES0</a> structure has the <b>FWPS_METADATA_FIELD_IP_HEADER_SIZE</b> flag set.</li>
<li>The <b>ipHeaderSize</b> member of the <a href="netvista.fwps_incoming_metadata_values0">FWPS_INCOMING_METADATA_VALUES0</a> structure is greater than zero.</li>
</ul>


At the following network layers, if the datagram belongs to a raw socket, the net buffer list pointed to by <i>netBufferList</i> must be adjusted to start at the IP header (which must be prepended to the net buffer list):<ul>
<li>
FWPS_LAYER_DATAGRAM_DATA_V4 (when outbound direction is specified with FWP_DIRECTION_OUTBOUND)
</li>
<li>
FWPS_LAYER_DATAGRAM_DATA_V6 (when outbound direction is specified with FWP_DIRECTION_OUTBOUND)
</li>
</ul>


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
Available starting with Windows Vista.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Fwpsk.h (include Fwpsk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Fwpkclnt.lib</dt>
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
<a href="netvista.classifyfn">classifyFn</a>
</dt>
<dt>
<a href="..\fwpsk\nc-fwpsk-fwps_inject_complete0.md">completionFn</a>
</dt>
<dt>
<a href="netvista.fwps_incoming_metadata_values0">
   FWPS_INCOMING_METADATA_VALUES0</a>
</dt>
<dt>
<a href="netvista.fwps_packet_injection_state">FWPS_PACKET_INJECTION_STATE</a>
</dt>
<dt>
<a href="netvista.fwps_transport_send_params0">FWPS_TRANSPORT_SEND_PARAMS0</a>
</dt>
<dt>
<a href="netvista.fwpsallocateclonenetbufferlist0">
   FwpsAllocateCloneNetBufferList0</a>
</dt>
<dt>
<a href="netvista.fwpsallocatenetbufferandnetbufferlist0">
   FwpsAllocateNetBufferAndNetBufferList0</a>
</dt>
<dt>
<a href="netvista.fwpsfreeclonenetbufferlist0">FwpsFreeCloneNetBufferList0</a>
</dt>
<dt>
<a href="netvista.fwpsfreenetbufferlist0">FwpsFreeNetBufferList0</a>
</dt>
<dt>
<a href="netvista.fwpsinjectionhandlecreate0">FwpsInjectionHandleCreate0</a>
</dt>
<dt>
<a href="netvista.fwpsinjectionhandledestroy0">FwpsInjectionHandleDestroy0</a>
</dt>
<dt>
<a href="netvista.fwpsinjecttransportsendasync1">FwpsInjectTransportSendAsync1</a>
</dt>
<dt>
<a href="netvista.fwpsquerypacketinjectionstate0">
   FwpsQueryPacketInjectionState0</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsInjectTransportSendAsync0 function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
