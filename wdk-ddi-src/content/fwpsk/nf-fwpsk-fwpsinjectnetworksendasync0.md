---
UID : NF:fwpsk.FwpsInjectNetworkSendAsync0
title : FwpsInjectNetworkSendAsync0 function
author : windows-driver-content
description : The FwpsInjectNetworkSendAsync0 function injects packet data into the send data path.Note  FwpsInjectNetworkSendAsync0 is a specific version of FwpsInjectNetworkSendAsync.
old-location : netvista\fwpsinjectnetworksendasync0.htm
old-project : netvista
ms.assetid : 9cc76bf7-a744-46f9-89d5-5277744221e5
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : fwpsk/FwpsInjectNetworkSendAsync0, FwpsInjectNetworkSendAsync0, netvista.fwpsinjectnetworksendasync0, FwpsInjectNetworkSendAsync0 function [Network Drivers Starting with Windows Vista], wfp_ref_2_funct_3_fwps_I_33cd70a5-56b6-4cb7-bebf-621e180aaa9b.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : fwpsk.h
req.include-header : Fwpsk.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows Vista.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Fwpkclnt.lib
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : FWPS_VSWITCH_EVENT_TYPE
---


# FwpsInjectNetworkSendAsync0 function
The 
  <b>FwpsInjectNetworkSendAsync0</b> function injects packet data into the send data path.
<div class="alert"><b>Note</b>  <b>FwpsInjectNetworkSendAsync0</b> is a specific version of <b>FwpsInjectNetworkSendAsync</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## Syntax

````
NTSTATUS NTAPI FwpsInjectNetworkSendAsync0(
  _In_     HANDLE                injectionHandle,
  _In_opt_ HANDLE                injectionContext,
  _In_     UINT32                flags,
  _In_     COMPARTMENT_ID        compartmentId,
  _Inout_  NET_BUFFER_LIST       *netBufferList,
  _In_     FWPS_INJECT_COMPLETE0 completionFn,
  _In_opt_ HANDLE                completionContext
);
````

## Parameters

`injectionHandle`

An injection handle that was previously created by a call to the 
     <a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandlecreate0.md">FwpsInjectionHandleCreate0</a> function with the 
     <i>flags</i> parameter set to FWPS_INJECTION_TYPE_NETWORK.

`injectionContext`

An optional handle to the injection context. If specified, it can be obtained by calling the 
     <a href="..\fwpsk\nf-fwpsk-fwpsquerypacketinjectionstate0.md">FwpsQueryPacketInjectionState0</a> function when the packet injection state 
     <a href="..\fwpsk\ne-fwpsk-fwps_packet_injection_state_.md">FWPS_PACKET_INJECTION_STATE</a> is
     <b>FWPS_PACKET_INJECTED_BY_SELF</b> or <b>FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF</b>.

`flags`

Reserved. Callout drivers must set this parameter to zero.

`compartmentId`

The identifier of the routing compartment into which the packet data is injected, specified as a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff542009">COMPARTMENT_ID</a> type. This identifier is provided
     to a callout through the 
     <b>compartmentId</b> member of the 
     <mshelp:link keywords="netvista.fwps_incoming_metadata_values0" tabindex="0"><b>
     FWPS_INCOMING_METADATA_VALUES0</b></mshelp:link> structure that is passed to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function. If the 
     <b>compartmentId</b> member is available to callouts, FWPS_METADATA_FIELD_COMPARTMENT_ID will be set in
     the 
     <b>currentMetadataValues</b> member. Otherwise, set this parameter to UNSPECIFIED_COMPARTMENT_ID.

`netBufferList`

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure that describes
     the packet data that is being injected. A callout driver allocates a NET_BUFFER_LIST structure to use to
     inject packet data by calling either the 
     <a href="..\fwpsk\nf-fwpsk-fwpsallocateclonenetbufferlist0.md">FwpsAllocateCloneNetBufferList0</a> function or the 
     <a href="..\fwpsk\nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0.md">FwpsAllocateNetBufferAndNetBufferList0</a> function. The NET_BUFFER_LIST structure must begin with an
     IP header.

`completionFn`

A pointer to a 
     <a href="..\fwpsk\nc-fwpsk-fwps_inject_complete0.md">completionFn</a> callout function provided by
     the callout driver. The filter engine calls this function after the packet data, described by the 
     <i>NetBufferList</i> parameter, has been injected into the network stack.

`completionContext`

A pointer to a callout driver-provided context that is passed to the callout function pointed to
     by the 
     <i>completionFn</i> parameter. This parameter is optional and can be <b>NULL</b>.


## Return Value

The 
     <b>FwpsInjectNetworkSendAsync0</b> function returns one of the following NTSTATUS codes.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The packet data injection was initiated successfully. The filter engine will call the completion
       function after the filter engine has completed injecting the packet data into the network stack, or
       when an error occurred subsequently. In case of an error, the 
       <b>Status</b> member of the completed NET_BUFFER_LIST structure will indicate the reason for
       failure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_TCPIP_NOT_READY</b></dt>
</dl>
</td>
<td width="60%">
The TCP/IP network stack is not ready to accept injection of packet data.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_INJECT_HANDLE_CLOSING</b></dt>
</dl>
</td>
<td width="60%">
The injection handle is being closed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_INJECT_HANDLE_STALE</b></dt>
</dl>
</td>
<td width="60%">
The injection handle was not created with the 
       <i>Flags</i> parameter of the 
       <mshelp:link keywords="netvista.fwpsinjectionhandlecreate0" tabindex="0"><b>
       FwpsInjectionHandleCreate0</b></mshelp:link> function set to FWPS_INJECTION_TYPE_NETWORK.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>

## Remarks

A callout driver calls the 
    <b>FwpsInjectNetworkSendAsync0</b> function to inject network packet data into the send data path. This
    function can execute asynchronously. Callout drivers normally inject data into the network stack when
    modifying packet data. For more information about how a callout driver can modify packet data, see 
    <a href="https://msdn.microsoft.com/24940254-c9ed-45f7-8a67-20978a8efd3f">Callout Driver Operations</a>.

If the return value is not STATUS_SUCCESS, the completion function will not be called. In this case,
    the net buffer list pointed to by 
    <i>netBufferList</i> needs to be freed by a call to the 
    <a href="..\fwpsk\nf-fwpsk-fwpsfreenetbufferlist0.md">FwpsFreeNetBufferList0</a> or 
    <mshelp:link keywords="netvista.fwpsfreeclonenetbufferlist0" tabindex="0"><b>
    FwpsFreeCloneNetBufferList0</b></mshelp:link> functions.

The injected packet can be indicated to the callout driver again. To prevent infinite looping, the
    driver should first call the 
    <mshelp:link keywords="netvista.fwpsquerypacketinjectionstate0" tabindex="0"><b>
    FwpsQueryPacketInjectionState0</b></mshelp:link> function before proceeding with a call to the 
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function, and the driver
    should permit packets that have the injection state 
    <a href="..\fwpsk\ne-fwpsk-fwps_packet_injection_state_.md">FWPS_PACKET_INJECTION_STATE</a> set to
    <b>FWPS_PACKET_INJECTED_BY_SELF</b> or <b>FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fwpsk.h (include Fwpsk.h) |
| **Library** |  |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** |  |

## See Also

<a href="..\fwpsk\nc-fwpsk-fwps_inject_complete0.md">completionFn</a>

<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>

<mshelp:link keywords="netvista.fwpsallocatenetbufferandnetbufferlist0" tabindex="0"><b>
   FwpsAllocateNetBufferAndNetBufferList0</b></mshelp:link>

<mshelp:link keywords="netvista.fwpsallocateclonenetbufferlist0" tabindex="0"><b>
   FwpsAllocateCloneNetBufferList0</b></mshelp:link>

<a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandledestroy0.md">FwpsInjectionHandleDestroy0</a>

<mshelp:link keywords="netvista.fwpsquerypacketinjectionstate0" tabindex="0"><b>
   FwpsQueryPacketInjectionState0</b></mshelp:link>

<mshelp:link keywords="netvista.fwps_incoming_metadata_values0" tabindex="0"><b>
   FWPS_INCOMING_METADATA_VALUES0</b></mshelp:link>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<a href="..\fwpsk\nf-fwpsk-fwpsfreeclonenetbufferlist0.md">FwpsFreeCloneNetBufferList0</a>

<a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandlecreate0.md">FwpsInjectionHandleCreate0</a>

<a href="..\fwpsk\nf-fwpsk-fwpsfreenetbufferlist0.md">FwpsFreeNetBufferList0</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsInjectNetworkSendAsync0 function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>