---
UID: NF:fwpsk.FwpsInjectMacSendAsync0
title: FwpsInjectMacSendAsync0 function
author: windows-driver-content
description: The FwpsInjectMacSendAsync0 function can reinject a previously absorbed media access control (MAC) frame (or a clone of the frame) back to the layer 2 outbound data path it was intercepted from, or inject an invented MAC frame.
old-location: netvista\fwpsinjectmacsendasync0.htm
old-project: netvista
ms.assetid: 9964D11C-C1A6-4BE7-A8A4-5A0E71801610
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FwpsInjectMacSendAsync0, FwpsInjectMacSendAsync0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsInjectMacSendAsync0, netvista.fwpsinjectmacsendasync0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	fwpkclnt.lib
-	fwpkclnt.dll
api_name:
-	FwpsInjectMacSendAsync0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---


# FwpsInjectMacSendAsync0 function
The <b>FwpsInjectMacSendAsync0</b> function can reinject a previously absorbed media access control (MAC) frame (or a clone of the frame) back to the layer 2 outbound data path it was intercepted from, or inject an invented MAC frame.<div class="alert"><b>Note</b>  <b>FwpsInjectMacSendAsync0</b> is a specific version of <b>FwpsInjectMacSendAsync</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>

## Syntax

````
NTSTATUS NTAPI FwpsInjectMacSendAsync0(
  _In_     HANDLE               injectionHandle,
  _In_opt_ HANDLE               injectionContext,
  _In_     UINT32               flags,
  _In_     UINT16               layerId,
  _In_     IF_INDEX             interfaceIndex,
  _In_     NDIS_PORT_NUMBER     NdisPortNumber,
  _Inout_  NET_BUFFER_LIST      *netBufferLists,
  _In_     FWPS_INJECT_COMPLETE completionFn,
  _In_opt_ HANDLE               completionContext
);
````

## Parameters

`injectionHandle`

An injection handle that was previously obtained by a call to  the <a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandlecreate0.md">FwpsInjectionHandleCreate0</a> function with the <i>flags</i> parameter set to FWPS_INJECTION_TYPE_L2. 

<div class="alert"><b>Note</b>  Set the <i>addressFamily</i> parameter of the <a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandlecreate0.md">FwpsInjectionHandleCreate0</a> function to AF_UNSPEC.</div>
<div> </div>

`injectionContext`

An optional handle to the injection context. If specified, it can be obtained by calling the 
     <a href="..\fwpsk\nf-fwpsk-fwpsquerypacketinjectionstate0.md">
     FwpsQueryPacketInjectionState0</a> function when the packet injection state 
     <a href="..\fwpsk\ne-fwpsk-fwps_packet_injection_state_.md">FWPS_PACKET_INJECTION_STATE</a> is
     <b>FWPS_PACKET_INJECTED_BY_SELF</b> or <b>FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF</b>.

`flags`

Reserved. Must be set to zero.

`layerId`

The run-time identifier for the filtering layer at which the data stream is being processed.

`interfaceIndex`

The interface index that is passed to the callout driver's <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> incoming value FWPS_FIELD_<i>Xxx</i>_MAC_FRAME_<i>Xxx</i>_INTERFACE_INDEX.

`NdisPortNumber`

The NDIS port number  that is passed to the callout driver's <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> incoming value FWPS_FIELD_<i>Xxx</i>_MAC_FRAME_<i>Xxx</i>_NDIS_PORT.

`netBufferLists`

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure that describes
     the packet data that is being injected. A callout driver allocates a NET_BUFFER_LIST structure to use to
     inject packet data by calling either the 
     <a href="..\fwpsk\nf-fwpsk-fwpsallocateclonenetbufferlist0.md">
     FwpsAllocateCloneNetBufferList0</a> function or the 
     <a href="..\fwpsk\nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0.md">
     FwpsAllocateNetBufferAndNetBufferList0</a> function. The NET_BUFFER_LIST structure must begin with an
     IP header.

`completionFn`

A pointer to a 
     <a href="..\fwpsk\nc-fwpsk-fwps_inject_complete0.md">completionFn</a> callout function provided by
     the callout driver. The filter engine calls this function after the packet data, described by the 
     <i>netBufferLists</i> parameter, has been injected into the network stack. This pointer must be specified when injecting cloned or created NET_BUFFER_LIST structures. When injecting original  NET_BUFFER_LIST structures, this parameter can be NULL if the  original structures  are not altered.

`completionContext`

A pointer to a callout driver–provided context that is passed to the callout function pointed to
     by the 
     <i>completionFn</i> parameter. This parameter is optional and can be <b>NULL</b>.


## Return Value

The 
     <b>FwpsInjectMacSendAsync0</b> function returns one of the following NTSTATUS codes.

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
The MAC frame injection was initiated successfully. The filter engine calls the completion
       function after the filter engine has completed injecting the MAC frame data, or
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
The MAC layer is not ready to accept injection of packet data.

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
       <i>flags</i> parameter of the 
       <a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandlecreate0.md">
       FwpsInjectionHandleCreate0</a> function set to FWPS_INJECTION_TYPE_L2.

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

A callback driver calls the <b>FwpsInjectMacSendAsync0</b>  function to reinject a previously absorbed MAC frame (or a clone of the frame) back to the layer 2 outbound data path that  it was intercepted from, or to inject an invented MAC frame.

The <i>netBufferLists</i> parameter can be a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> chain. However the completion function could be invoked multiple times each, completing a segment (or single NET_BUFFER_LIST) of the chain.



Injected frames could get classified again if the packets match the same filter as originally classified. Therefore, as with callouts at IP layers, layer 2 callouts must also protect against infinite packet inspection by calling <a href="..\fwpsk\nf-fwpsk-fwpsquerypacketinjectionstate0.md">FwpsQueryPacketInjectionState0</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.  |
| **Target Platform** | Universal |
| **Header** | fwpsk.h (include Fwpsk.h) |
| **Library** | Fwpkclnt.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\fwpsk\nf-fwpsk-fwpsallocateclonenetbufferlist0.md">
     FwpsAllocateCloneNetBufferList0</a>



<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>



<a href="..\fwpsk\nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0.md">
     FwpsAllocateNetBufferAndNetBufferList0</a>



<a href="..\fwpsk\nf-fwpsk-fwpsquerypacketinjectionstate0.md">FwpsQueryPacketInjectionState0</a>



<a href="..\fwpsk\nc-fwpsk-fwps_inject_complete0.md">completionFn</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandlecreate0.md">
       FwpsInjectionHandleCreate0</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsInjectMacSendAsync0 function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>