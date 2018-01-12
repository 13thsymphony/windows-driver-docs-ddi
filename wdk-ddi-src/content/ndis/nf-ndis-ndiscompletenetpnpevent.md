---
UID: NF:ndis.NdisCompleteNetPnPEvent
title: NdisCompleteNetPnPEvent function
author: windows-driver-content
description: Protocol drivers call the NdisCompleteNetPnPEvent function to complete a response to a Plug and Play or Power Management event for which the caller's ProtocolNetPnPEvent function returned NDIS_STATUS_PENDING.
old-location: netvista\ndiscompletenetpnpevent.htm
old-project: netvista
ms.assetid: 2a59e6a1-d018-4b95-8e50-8351a3b69d86
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: NdisCompleteNetPnPEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisCompleteNetPnPEvent
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Protocol_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisCompleteNetPnPEvent function



## -description
Protocol drivers call the 
  <b>NdisCompleteNetPnPEvent</b> function to complete a response to a Plug and Play or Power Management event
  for which the caller's 
  <a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">ProtocolNetPnPEvent</a> function returned
  NDIS_STATUS_PENDING.



## -syntax

````
VOID NdisCompleteNetPnPEvent(
  _In_ NDIS_HANDLE                 NdisBindingHandle,
  _In_ PNET_PNP_EVENT_NOTIFICATION NetPnPEvent,
  _In_ NDIS_STATUS                 Status
);
````


## -parameters

### -param NdisBindingHandle [in]

The handle that NDIS provided at the 
     <i>NdisBindingHandle</i> parameter of the 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function. The handle
     identifies the binding between the caller and the underlying miniport adapter.


### -param NetPnPEvent [in]

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_pnp_event_notification.md">
     NET_PNP_EVENT_NOTIFICATION</a> structure that NDIS passed to the caller's 
     <a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">
     ProtocolNetPnPEvent</a> function.


### -param Status [in]

The protocol driver's response to the pending Plug and Play or Power Management event
     notification. To succeed such an event, specify NDIS_STATUS_SUCCESS. For information about other status
     values, see the return values of the 
     <a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">
     ProtocolNetPnPEvent</a> function.


## -returns
None


## -remarks
When a protocol driver returns NDIS_STATUS_PENDING from its 
    <a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">ProtocolNetPnPEvent</a> function, it
    must eventually call 
    <b>NdisCompleteNetPnPEvent</b> to indicate its response to the given Plug and Play or Power Management
    notification.


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
PASSIVE_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547996">Irql_Protocol_Driver_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_pnp_event_notification.md">NET_PNP_EVENT_NOTIFICATION</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_net_pnp_event.md">ProtocolNetPnPEvent</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCompleteNetPnPEvent function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

