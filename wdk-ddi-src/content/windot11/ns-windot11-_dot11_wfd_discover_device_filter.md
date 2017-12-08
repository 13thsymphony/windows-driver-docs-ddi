---
UID: NS.WINDOT11._DOT11_WFD_DISCOVER_DEVICE_FILTER
title: _DOT11_WFD_DISCOVER_DEVICE_FILTER
author: windows-driver-content
description: The DOT11_WFD_DISCOVER _DEVICE_FILTER structure describes a P2P device and Group Owner filter when responding to OID_DOT11_WFD_DISCOVERY_REQUEST requests.
old-location: netvista\dot11_wfd_discover_device_filter.htm
old-project: netvista
ms.assetid: B8AA23C6-EFFC-47C3-9AD2-72421463CDBA
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DOT11_WFD_DISCOVER_DEVICE_FILTER, *PDOT11_WFD_DISCOVER_DEVICE_FILTER, DOT11_WFD_DISCOVER_DEVICE_FILTER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_WFD_DISCOVER_DEVICE_FILTER
req.alt-loc: Windot11.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# _DOT11_WFD_DISCOVER_DEVICE_FILTER structure



## -description

## -syntax

````
typedef struct _DOT11_WFD_DISCOVER_DEVICE_FILTER {
  DOT11_MAC_ADDRESS DeviceID;
  UCHAR             ucBitmask;
  DOT11_SSID        GroupSSID;
} DOT11_WFD_DISCOVER_DEVICE_FILTER, *PDOT11_WFD_DISCOVER_DEVICE_FILTER;
````


## -struct-fields

### -field DeviceID

The device address of a P2P Device or Group Owner to be discovered by the local P2P device.

### -field ucBitmask

Filters which instances of the P2P device to discover. Possible values include:

<table>
<tr>
<th>Term</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<a id="DISCOVERY_FILTER_BITMASK_DEVICE"></a><a id="discovery_filter_bitmask_device"></a>DISCOVERY_FILTER_BITMASK_DEVICE
</td>
<td width="60%">
The local P2P device discovers the P2P device with the desired <b>DeviceID</b>.
</td>
</tr>
<tr>
<td width="40%">
<a id="_DISCOVERY_FILTER_BITMASK_GO"></a><a id="_discovery_filter_bitmask_go"></a> DISCOVERY_FILTER_BITMASK_GO
</td>
<td width="60%">
The local P2P device discovers a group with P2P group ID matching the specified <b>DeviceID</b> and <b>GroupSSID</b>.
</td>
</tr>
<tr>
<td width="40%">
<a id="DISCOVERY_FILTER_BITMASK_ANY"></a><a id="discovery_filter_bitmask_any"></a>DISCOVERY_FILTER_BITMASK_ANY
</td>
<td width="60%">
 The local P2P device needs only to discover the P2P device or any group owner hosted by the P2P device.
</td>
</tr>
</table>
 

### -field GroupSSID

If GroupSSID is not a zero-length SSID, this member specifies the SSID of a P2P group that the local P2P device discovers. If this is the P2P wildcard SSID ("DIRECT-"), the local P2P device discovers all groups with P2P Group ID matching the desired device ID.

## -remarks
The local P2P device should not extend the discovery operation to find additional instances.

Note that if the value of <b>ucBitmask</b> is FILTER_BITMASK_DEVICE | FILTER_BITMASK_GO, the local P2P device should discover only one instance of the P2P device - either the P2P device or a GO with the desired P2P <b>DeviceID</b> and <b>GroupSSID</b>.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Versions: Supported in Windows 8
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Windot11.h (include Windot11.h)</dt>
</dl>
</td>
</tr>
</table>