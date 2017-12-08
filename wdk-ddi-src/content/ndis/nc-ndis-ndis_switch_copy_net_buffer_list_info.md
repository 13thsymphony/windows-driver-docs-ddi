---
UID: NC.ndis.NDIS_SWITCH_COPY_NET_BUFFER_LIST_INFO
title: NDIS_SWITCH_COPY_NET_BUFFER_LIST_INFO
author: windows-driver-content
description: The Hyper-V extensible switch extension calls the CopyNetBufferListInfo function to copy the out-of-band (OOB) forwarding context from a source packet's NET_BUFFER_LIST structure to a destination packet's NET_BUFFER_LIST structure.
old-location: netvista\CopyNetBufferListInfo.htm
old-project: netvista
ms.assetid: 5CC345FA-C3EF-4122-8E9C-6EA27B20DD5A
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CopyNetBufferListInfo
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# NDIS_SWITCH_COPY_NET_BUFFER_LIST_INFO callback



## -description

The Hyper-V extensible switch extension calls the <i>CopyNetBufferListInfo</i> function to copy the out-of-band (OOB) forwarding context from a source packet's <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure to a destination packet's <b>NET_BUFFER_LIST</b> structure. This context includes the extensible switch source port and network adapter information. The extensible switch destination port information can also be copied.

The Hyper-V extensible switch extension calls the <i>CopyNetBufferListInfo</i> function to copy the out-of-band (OOB) forwarding context from a source packet's <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure to a destination packet's <b>NET_BUFFER_LIST</b> structure. This context includes the extensible switch source port and network adapter information. The extensible switch destination port information can also be copied.


## -prototype

````
NDIS_SWITCH_COPY_NET_BUFFER_LIST_INFO CopyNetBufferListInfo;

NDIS_STATUS CopyNetBufferListInfo(
  _In_    NDIS_SWITCH_CONTEXT NdisSwitchContext,
  _Inout_ PNET_BUFFER_LIST    DestNetBufferList,
  _In_    PNET_BUFFER_LIST    SrcNetBufferList,
  _In_    UINT32              Flags
)
{ ... }
````


## -parameters

### -param NdisSwitchContext [in]

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the extension is attached. When the extension calls <a href="netvista.ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.

### -param DestNetBufferList [in, out]

A pointer to a <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure for the destination packet to which the extensible switch forwarding context is copied.  

### -param SrcNetBufferList [in]

A pointer to a <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure for the source packet from which the extensible switch forwarding context is copied. 

### -param Flags [in]

A UINT32 value. When the NDIS_SWITCH_COPY_NBL_INFO_FLAGS_PRESERVE_DESTINATIONS flag is specified, the function copies the extensible switch destination ports from the source packet to the destination packet.
The data that is contained within the source packet's <a href="netvista.ndis_switch_forwarding_detail_net_buffer_list_info">NDIS_SWITCH_FORWARDING_DETAIL_NET_BUFFER_LIST_INFO</a> union is always copied to the extensible switch forwarding context in the destination packet. This data includes the source port identifiers and index of the network adapter connection from which the packet originated. Depending on the number of extensible switch destination ports that are copied to the destination packet, the NumAvailableDestinations member of the <b>NDIS_SWITCH_FORWARDING_DETAIL_NET_BUFFER_LIST_INFO</b> union is updated in the destination packet.
For more information about the forwarding context, see <a href="netvista.hyper_v_extensible_switch_forwarding_context">Hyper-V Extensible Switch Forwarding Context</a>.

## -returns
If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.



## -remarks
The extensible switch extension calls the <i>CopyNetBufferListInfo</i> function to copy the OOB data from a source packet to a destination packet. This data includes the following:

The data from the <b>NetBufferListInfo</b> array of the source packet's <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure.

The <a href="netvista.ndis_switch_forwarding_detail_net_buffer_list_info">NDIS_SWITCH_FORWARDING_DETAIL_NET_BUFFER_LIST_INFO</a> data from the source packet's extensible switch forwarding context.

The data for the extensible switch destination ports from the source packet's extensible switch forwarding context.

Before the extension calls <i>CopyNetBufferListInfo</i>, it must prepare the destination packet's <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure by following these steps:

The extension must first initialize a <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure for the destination packet that is derived from the source packet's  <b>NET_BUFFER_LIST</b> structure. 

For example, the extension can call <a href="netvista.ndisallocateclonenetbufferlist">NdisAllocateCloneNetBufferList</a> to create a complete copy of the source packet. The extension can also call <a href="netvista.ndisallocatefragmentnetbufferlist">NdisAllocateFragmentNetBufferList</a> to create a copy of only a fragment of the source packet. For more information, see <a href="netvista.derived_net_buffer_list_structures">Derived NET_BUFFER_LIST Structures</a>.

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
Supported in NDIS 6.30 and later.
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
IRQL
</th>
<td width="70%">
&lt;= DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="netvista.AllocateNetBufferListForwardingContext">AllocateNetBufferListForwardingContext</a>
</dt>
<dt>
<a href="netvista.ndisallocateclonenetbufferlist">NdisAllocateCloneNetBufferList</a>
</dt>
<dt>
<a href="netvista.ndisallocatefragmentnetbufferlist">NdisAllocateFragmentNetBufferList</a>
</dt>
<dt>
<a href="netvista.ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="netvista.ndis_switch_forwarding_detail_net_buffer_list_info">NDIS_SWITCH_FORWARDING_DETAIL_NET_BUFFER_LIST_INFO</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_COPY_NET_BUFFER_LIST_INFO callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
