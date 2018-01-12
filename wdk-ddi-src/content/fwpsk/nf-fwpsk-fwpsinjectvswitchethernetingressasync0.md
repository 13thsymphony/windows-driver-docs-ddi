---
UID: NF:fwpsk.FwpsInjectvSwitchEthernetIngressAsync0
title: FwpsInjectvSwitchEthernetIngressAsync0 function
author: windows-driver-content
description: The FwpsInjectvSwitchEthernetIngressAsync0 (was FwpsInjectvSwitchIngressAsync0) function reinjects a previously absorbed virtual switch packet (unmodified) back to the virtual switch ingress data path where it was intercepted.
old-location: netvista\fwpsinjectvswitchingressasync0.htm
old-project: netvista
ms.assetid: ccb22035-08fe-44a6-88d5-bf9db7c2f499
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: FwpsInjectvSwitchEthernetIngressAsync0
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
req.alt-api: FwpsInjectvSwitchEthernetIngressAsync0
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

# FwpsInjectvSwitchEthernetIngressAsync0 function



## -description
The <b>FwpsInjectvSwitchEthernetIngressAsync0</b> (was <b>FwpsInjectvSwitchIngressAsync0</b>) function reinjects a previously absorbed virtual switch packet (unmodified) back to the virtual switch ingress data path where it was intercepted. This function can also inject a packet created with  the <a href="..\fwpsk\nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0.md">FwpsAllocateNetBufferAndNetBufferList0</a>  function.



## -syntax

````
NTSTATUS NTAPI FwpsInjectvSwitchEthernetIngressAsync0(
  _In_           HANDLE                  injectionHandle,
  _In_opt_       HANDLE                  injectionContext,
  _In_           _Reserved_ UINT32       flags,
  _In_opt_       _Reserved_ void         *reserved,
  _In_     const FWP_BYTE_BLOB           *vSwitchId,
  _In_           NDIS_SWITCH_PORT_ID     vSwitchSourcePortId,
  _In_           NDIS_SWITCH_NIC_INDEX   vSwitchSourceNicIndex,
                 _Inout_ NET_BUFFER_LIST *netBufferLists,
  _In_           FWPS_INJECT_COMPLETE    completionFn,
  _In_opt_       HANDLE                  completionContext
);
````


## -parameters

### -param injectionHandle [in]

An injection handle that was previously created by a call to the <a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandlecreate0.md">FwpsInjectionHandleCreate0</a> function with the <i>flags</i> parameter set to <b>FWPS_INJECTION_TYPE_VSWITCH</b>.


The <i>addressFamily</i> parameter is not used and should be set to <b>AF_UNSPEC</b>.



### -param injectionContext [in, optional]

An optional handle to the injection context that can be  retrieved with the <a href="..\fwpsk\nf-fwpsk-fwpsquerypacketinjectionstate0.md">FwpsQueryPacketInjectionState0</a> function.


### -param flags [in]

Reserved. Must be set to zero.


### -param reserved [in, optional]

Reserved. Must be set to NULL.


### -param vSwitchId [in]

The virtual  switch identifier that the filtering engine passed in the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552401">FWPS_INCOMING_VALUES0</a> structure to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function. This is the  <b>GUID</b> of the virtual switch that is provided in an xxx_VSWITCH_ID field. 


### -param vSwitchSourcePortId [in]

The virtual  switch source port identifier. 


### -param vSwitchSourceNicIndex [in]

The virtual  switch source NIC  index.


### -param netBufferLists 

A chain of <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures to be injected into the virtual switch egress data path.


### -param completionFn [in]

A pointer to a 
     <a href="..\fwpsk\nc-fwpsk-fwps_inject_complete0.md">completionFn</a> callout function that is provided by
     the callout driver. The filter engine calls this function after the packet data, at the 
     <i>netBufferLists</i> parameter, has been injected into the virtual switch egress data path. The 
     <i>completionFn</i> function will be called once for each <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> in the chain. <i>completionFn</i> must be specified when injecting cloned or created <b>NET_BUFFER_LIST</b> structures. This parameter can be NULL when injecting original unaltered <b>NET_BUFFER_LIST</b> structures that were received from the filter engine. 


### -param completionContext [in, optional]

A pointer to a callout driver–provided context that is passed to the callout function pointed to
     by the 
     <i>completionFn</i> parameter. This parameter is optional and can be <b>NULL</b>.


## -returns
The 
     <b>FwpsInjectvSwitchEthernetIngressAsync0</b> function returns one of the following <b>NTSTATUS</b> codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The virtual switch <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> chain was successfully injected.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 


## -remarks


When a callout injects packets with <b>FwpsInjectvSwitchEthernetIngressAsync0</b>, the injected packets could be classified again if the packets match the same filter as they were originally classified. Therefore, like callouts at IP layers, virtual switch callouts must call the <a href="..\fwpsk\nf-fwpsk-fwpsquerypacketinjectionstate0.md">FwpsQueryPacketInjectionState0</a> function to protect against infinite packet inspections.


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
<a href="..\fwpsk\nc-fwpsk-fwps_inject_complete0.md">completionFn</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552401">FWPS_INCOMING_VALUES0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0.md">FwpsAllocateNetBufferAndNetBufferList0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandlecreate0.md">FwpsInjectionHandleCreate0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsquerypacketinjectionstate0.md">FwpsQueryPacketInjectionState0</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsInjectvSwitchEthernetIngressAsync0 function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

