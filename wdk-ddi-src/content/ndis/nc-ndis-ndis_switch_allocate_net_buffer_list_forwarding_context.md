---
UID: NC.ndis.NDIS_SWITCH_ALLOCATE_NET_BUFFER_LIST_FORWARDING_CONTEXT
title: NDIS_SWITCH_ALLOCATE_NET_BUFFER_LIST_FORWARDING_CONTEXT
author: windows-driver-content
description: The AllocateNetBufferListForwardingContext function prepares a NET_BUFFER_LIST structure for send or receive operations within the extensible switch.
old-location: netvista\AllocateNetBufferListForwardingContext.htm
old-project: netvista
ms.assetid: C8A80DB2-4273-4FBA-82D4-4E8146812B16
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
req.alt-api: AllocateNetBufferListForwardingContext
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

# NDIS_SWITCH_ALLOCATE_NET_BUFFER_LIST_FORWARDING_CONTEXT callback



## -description

The <i>AllocateNetBufferListForwardingContext</i> function prepares a <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure for send or receive operations within the extensible switch.

The <i>AllocateNetBufferListForwardingContext</i> function prepares a <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure for send or receive operations within the extensible switch.


## -prototype

````
NDIS_SWITCH_ALLOCATE_NET_BUFFER_LIST_FORWARDING_CONTEXT AllocateNetBufferListForwardingContext;

NDIS_STATUS AllocateNetBufferListForwardingContext(
  _In_    NDIS_SWITCH_CONTEXT NdisSwitchContext,
  _Inout_ PNET_BUFFER_LIST    NetBufferList
)
{ ... }
````


## -parameters

### -param NdisSwitchContext [in]

An NDIS_SWITCH_CONTEXT value that contains the handle of the extensible switch module to which the Hyper-V extensible switch extension is attached. When the extension calls <a href="netvista.ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>,  this handle is returned through the <i>NdisSwitchContext</i> parameter.

### -param NetBufferList [in, out]

A pointer to a linked list of <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structures. 

## -returns
If the call succeeds, the function returns NDIS_STATUS_SUCCESS. Otherwise, it returns an NDIS_STATUS_<i>Xxx</i> error code that is defined in Ndis.h.



## -remarks
The extensible switch extension can originate packet send operations within the extensible switch data path. For example, the extension can send packets to any port on the extensible switch. For more information about this data path, see <a href="netvista.hyper_v_extensible_switch_data_path">Hyper-V Extensible Switch Data Path</a>.

After the extension calls <a href="netvista.ndisallocatenetbufferlist">NdisAllocateNetBufferList</a> or <a href="netvista.ndisallocateclonenetbufferlist">NdisAllocateCloneNetBufferList</a> to create or clone a packet from its <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> pool, the extension must  call the <i>AllocateNetBufferListForwardingContext</i> function. This function allocates and initializes the out-of-band (OOB) extensible switch forwarding context for the specified  <b>NET_BUFFER_LIST</b> structure. For more information about this context, see <a href="netvista.hyper_v_extensible_switch_forwarding_context">Hyper-V Extensible Switch Forwarding Context</a>.

The extension must follow these guidelines for allocating the forwarding context through the <i>AllocateNetBufferListForwardingContext</i> function:

The extension calls <a href="netvista.ndisallocatenetbufferlist">NdisAllocateNetBufferList</a> to allocate a packet from the extension's <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> pool for a send or receive operation over the extensible switch. Before the extension initializes source and destination ports for the packet, it must call <i>AllocateNetBufferListForwardingContext</i>. 

For more information on how to specify source and destination extensible switch ports, see <a href="netvista.managing_hyper_v_extensible_switch_source_and_destination_port_data">Managing Hyper-V Extensible Switch Source and Destination Port Data</a>.

Before the extension calls <i>AllocateNetBufferListForwardingContext</i>, it must set the <b>SourceHandle</b> member of each allocated <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure to the handle value that identifies the extension. The extension receives this handle through the <i>NdisFilterHandle</i> parameter when NDIS calls the extension's <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.

When the send operation is complete, the extension must call the <a href="netvista.FreeNetBufferListForwardingContext">FreeNetBufferListForwardingContext</a> function to deallocate the resources for the forwarding context. The extension must call this function before it calls <a href="netvista.ndisfreenetbufferlist">NdisFreeNetBufferList</a> to return the packet to its <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> pool.

If the extension is cloning a packet, it must call <a href="netvista.CopyNetBufferListInfo">CopyNetBufferListInfo</a> to copy the forwarding context from the original packet to the cloned packet. The extension must do this after it calls <i>AllocateNetBufferListForwardingContext</i>.

 For more information on how to originate send operations, see <a href="netvista.filter_module_send_and_receive_operations">Filter Module Send and Receive Operations</a>.

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
<a href="netvista.CopyNetBufferListInfo">CopyNetBufferListInfo</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>
</dt>
<dt>
<a href="netvista.FreeNetBufferListForwardingContext">FreeNetBufferListForwardingContext</a>
</dt>
<dt>
<a href="netvista.ndisallocatenetbufferlist">NdisAllocateNetBufferList</a>
</dt>
<dt>
<a href="netvista.ndisfgetoptionalswitchhandlers">NdisFGetOptionalSwitchHandlers</a>
</dt>
<dt>
<a href="netvista.ndisfreenetbufferlist">NdisFreeNetBufferList</a>
</dt>
<dt>
<a href="netvista.net_buffer">NET_BUFFER</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_ALLOCATE_NET_BUFFER_LIST_FORWARDING_CONTEXT callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
