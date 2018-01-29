---
UID : NF:ndis.NdisFNetPnPEvent
title : NdisFNetPnPEvent function
author : windows-driver-content
description : A filter driver can call the NdisFNetPnPEvent function to forward a network Plug and Play (PnP) or Power Management event to overlying drivers.
old-location : netvista\ndisfnetpnpevent.htm
old-project : netvista
ms.assetid : 383f9dcb-68ba-4323-b25f-668169043f35
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.ndisfnetpnpevent, filter_ndis_functions_ref_36921970-788b-4b5e-9cf0-c54f8dcdeef2.xml, NdisFNetPnPEvent function [Network Drivers Starting with Windows Vista], NdisFNetPnPEvent, ndis/NdisFNetPnPEvent
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Desktop
req.target-min-winverclnt : Supported in NDIS 6.0 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : Irql_Filter_Driver_Function
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisFNetPnPEvent function
A filter driver can call the 
  <b>NdisFNetPnPEvent</b> function to forward a network Plug and Play (PnP) or Power Management event to
  overlying drivers.

## Syntax

````
NDIS_STATUS NdisFNetPnPEvent(
  _In_ NDIS_HANDLE                 FilterModuleContext,
  _In_ PNET_PNP_EVENT_NOTIFICATION NetPnPEvent
);
````

## Parameters

`NdisFilterHandle`

TBD

`NetPnPEventNotification`

TBD


## Return Value

<b>NdisFNetPnPEvent</b> can return either of the following:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The overlying driver succeeded in processing the PnP event.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The overlying driver failed the PnP event.

</td>
</tr>
</table>

## Remarks

NDIS calls a filter driver's 
    <a href="..\ndis\nc-ndis-filter_net_pnp_event.md">FilterNetPnPEvent</a> function to notify
    the filter driver of network PnP and Power Management events.

Filter drivers can forward these notifications to overlying drivers. To forward a request, call the 
    <b>NdisFNetPnPEvent</b> function from 
    <i>FilterNetPnPEvent</i>.
<div class="alert"><b>Note</b>  NDIS drivers must not call 
    <b>NdisFNetPnPEvent</b> from within the context of the 
    <a href="..\ndis\nc-ndis-filter_oid_request.md">FilterOidRequest</a> function.</div><div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | Irql_Filter_Driver_Function |

## See Also

<a href="..\ndis\nc-ndis-filter_net_pnp_event.md">FilterNetPnPEvent</a>

<a href="..\ndis\nc-ndis-filter_oid_request.md">FilterOidRequest</a>

<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>

<a href="..\ndis\ns-ndis-_net_pnp_event_notification.md">NET_PNP_EVENT_NOTIFICATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFNetPnPEvent function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>