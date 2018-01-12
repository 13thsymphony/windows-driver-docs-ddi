---
UID: NF:fwpsk.FwpsInjectMacReceiveAsync0
title: FwpsInjectMacReceiveAsync0 function
author: windows-driver-content
description: The FwpsInjectMacReceiveAsync0 function can reinject a previously absorbed media access control (MAC) frame (or a clone of the frame) back to the layer 2 inbound data path it was intercepted from, or inject an invented MAC frame.
old-location: netvista\fwpsinjectmacreceiveasync0.htm
old-project: netvista
ms.assetid: 8B03835A-98EE-4157-BD05-C52D01EE5F5E
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: FwpsInjectMacReceiveAsync0
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
req.alt-api: FwpsInjectMacSendAsync0
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
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsInjectMacReceiveAsync0 function



## -description
The <b>FwpsInjectMacReceiveAsync0</b> function can  reinject a previously absorbed media access control (MAC) frame (or a clone of the frame) back to the layer 2 inbound data path it was intercepted from, or inject an invented MAC frame.<div class="alert"><b>Note</b>  <b>FwpsInjectMacReceiveAsync0</b> is a specific version of <b>FwpsInjectMacReceiveAsync</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>




## -syntax

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


## -parameters

### -param injectionHandle [in]

An injection handle that was previously obtained by a call to  the <a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandlecreate0.md">FwpsInjectionHandleCreate0</a> function with the <i>flags</i> parameter set to FWPS_INJECTION_TYPE_L2. 

<div class="alert"><b>Note</b>  Set the <i>addressFamily</i> parameter of the <a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandlecreate0.md">FwpsInjectionHandleCreate0</a> function to AF_UNSPEC.</div>
<div> </div>

### -param injectionContext [in, optional]

An optional handle to the injection context. If specified, it can be obtained by calling the 
     <a href="..\fwpsk\nf-fwpsk-fwpsquerypacketinjectionstate0.md">
     FwpsQueryPacketInjectionState0</a> function when the packet injection state 
     <a href="..\fwpsk\ne-fwpsk-fwps_packet_injection_state_.md">FWPS_PACKET_INJECTION_STATE</a> is
     <b>FWPS_PACKET_INJECTED_BY_SELF</b> or <b>FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF</b>.


### -param flags [in]

Reserved. Must be set to zero.


### -param layerId [in]

The run-time identifier for the filtering layer at which the data stream is being processed. 


### -param interfaceIndex [in]

The interface index that is passed to the callout driver's <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> incoming value FWPS_FIELD_<i>Xxx</i>_MAC_FRAME_<i>Xxx</i>_INTERFACE_INDEX.


### -param NdisPortNumber [in]

The NDIS port number  that is passed to the callout driver's <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> incoming value FWPS_FIELD_<i>Xxx</i>_MAC_FRAME_<i>Xxx</i>_NDIS_PORT.


### -param netBufferLists [in, out]

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure that describes
     the packet data that is being injected. A callout driver allocates a NET_BUFFER_LIST structure to use to
     inject packet data by calling either the 
     <a href="..\fwpsk\nf-fwpsk-fwpsallocateclonenetbufferlist0.md">FwpsAllocateCloneNetBufferList0</a> function or the 
     <a href="..\fwpsk\nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0.md">FwpsAllocateNetBufferAndNetBufferList0</a> function. The NET_BUFFER_LIST structure must begin with an
     IP header.


### -param completionFn [in]

A pointer to a 
     <a href="..\fwpsk\nc-fwpsk-fwps_inject_complete0.md">completionFn</a> callout function provided by
     the callout driver. The filter engine calls this function after the packet data, described by the 
     <i>netBufferLists</i> parameter, has been injected into the network stack. This pointer must be specified when injecting cloned or created NET_BUFFER_LIST structures. When injecting original  NET_BUFFER_LIST structures, this parameter can be NULL if the original structures  are not altered.


### -param completionContext [in, optional]

A pointer to a callout driver–provided context that is passed to the callout function pointed to
     by the 
     <i>completionFn</i> parameter. This parameter is optional and can be <b>NULL</b>.


## -returns
The 
     <b>FwpsInjectMacReceiveAsync0</b> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The MAC frame data injection was initiated successfully. The filter engine calls the completion
       function after the filter engine has completed injecting the MAC frame data, or
       when an error occurred subsequently. In case of an error, the 
       <b>Status</b> member of the completed 
       <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure will indicate
       the reason for failure.
<dl>
<dt><b>STATUS_FWP_TCPIP_NOT_READY</b></dt>
</dl>The MAC layer is not ready to accept injection of packet data.
<dl>
<dt><b>STATUS_FWP_INJECT_HANDLE_CLOSING</b></dt>
</dl>The injection handle is being closed.
<dl>
<dt><b>STATUS_FWP_INJECT_HANDLE_STALE</b></dt>
</dl>The injection handle was not created with the 
       <i>flags</i> parameter of the 
       <a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandlecreate0.md">
       FwpsInjectionHandleCreate0</a> function set to FWPS_INJECTION_TYPE_L2.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 


## -remarks
A callback driver calls the <b>FwpsInjectMacReceiveAsync0</b>  function to reinject a previously absorbed MAC frame (or a clone of the frame) back to the layer 2 inbound data path it was intercepted from, or to inject an invented MAC frame.

The <i>netBufferLists</i> parameter can be a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> chain. However the completion function could be invoked multiple times each, completing a segment (or single NET_BUFFER_LIST) of the chain.



Injected frames could get classified again if the packets match the same filter as originally classified. Therefore, as with callouts at IP layers, layer 2 callouts must also protect against infinite packet inspection by calling <a href="..\fwpsk\nf-fwpsk-fwpsquerypacketinjectionstate0.md">FwpsQueryPacketInjectionState0</a>.



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
Available starting with Windows 8.

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
<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>
</dt>
<dt>
<a href="..\fwpsk\nc-fwpsk-fwps_inject_complete0.md">completionFn</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsallocateclonenetbufferlist0.md">
     FwpsAllocateCloneNetBufferList0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0.md">
     FwpsAllocateNetBufferAndNetBufferList0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandlecreate0.md">
       FwpsInjectionHandleCreate0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsquerypacketinjectionstate0.md">FwpsQueryPacketInjectionState0</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsInjectMacReceiveAsync0 function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

