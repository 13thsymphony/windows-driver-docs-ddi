---
UID: NF.ndis.NdisFDevicePnPEventNotify
title: NdisFDevicePnPEventNotify function
author: windows-driver-content
description: A filter driver can call the NdisFDevicePnPEventNotify function to forward a device Plug and Play (PnP) or Power Management event to underlying drivers.
old-location: netvista\ndisfdevicepnpeventnotify.htm
old-project: netvista
ms.assetid: ae5dd48b-7777-4232-89ad-ac4464e03e57
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: NdisFDevicePnPEventNotify
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
req.alt-api: NdisFDevicePnPEventNotify
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Filter_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# NdisFDevicePnPEventNotify function



## -description
A filter driver can call the 
  <b>NdisFDevicePnPEventNotify</b> function to forward a device Plug and Play (PnP) or Power Management event
  to underlying drivers.


## -syntax

````
VOID NdisFDevicePnPEventNotify(
  _In_ NDIS_HANDLE           NdisFilterHandle,
  _In_ PNET_DEVICE_PNP_EVENT NetDevicePnPEvent
);
````


## -parameters

### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.

### -param NetDevicePnPEvent [in]

A pointer to a 
     <a href="netvista.net_device_pnp_event">NET_DEVICE_PNP_EVENT</a> structure that
     describes a device Plug and Play event.

## -returns
None

## -remarks
NDIS calls a filter driver's 
    <a href="..\ndis\nc-ndis-filter_device_pnp_event_notify.md">
    FilterDevicePnPEventNotify</a> function to notify the filter driver of device PnP and Power Management
    events that affect an underlying device object.

Filter drivers can forward these notifications to underlying drivers. To forward a request, call the 
    <b>NdisFDevicePnPEventNotify</b> function before returning from the 
    <i>FilterDevicePnPEventNotify</i> function.

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
<a href="devtest.ndis_irql_filter_driver_function">Irql_Filter_Driver_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_device_pnp_event_notify.md">FilterDevicePnPEventNotify</a>
</dt>
<dt>
<a href="netvista.net_device_pnp_event">NET_DEVICE_PNP_EVENT</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFDevicePnPEventNotify function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
