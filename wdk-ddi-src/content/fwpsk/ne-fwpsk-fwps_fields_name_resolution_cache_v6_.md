---
UID: NE.fwpsk.FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6_
title: FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6_
author: windows-driver-content
description: The FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6 enumeration type specifies the data field identifiers for the FWPS_LAYER_NAME_RESOLUTION_CACHE_V6 run-time filtering layer.
old-location: netvista\fwps_fields_name_resolution_cache_v6.htm
old-project: NetVista
ms.assetid: 78d2ec8f-fbee-4bad-bc84-b10495c24399
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6_, FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6
req.alt-loc: fwpsk.h
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

# FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6_ enumeration



## -description
The FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6 enumeration type specifies the data field identifiers for
  the FWPS_LAYER_NAME_RESOLUTION_CACHE_V6 
  <a href="netvista.run_time_filtering_layer_identifiers">run-time filtering layer</a>.



## -syntax

````
typedef enum FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6_ { 
  FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_ALE_USER_ID,
  FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_ALE_APP_ID,
  FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_IP_REMOTE_ADDRESS,
  FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_PEER_NAME,
  FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_MAX
} FWPS_FIELDS_NAME_RESOLUTION_CACHE_V6;
````


## -enum-fields

### -field FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_ALE_USER_ID

The identifier of the local user.


### -field FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_ALE_APP_ID

The full path of the application.


### -field FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_IP_REMOTE_ADDRESS

The remote IP address.


### -field FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_PEER_NAME

The machine name that is associated with the destination IP address.


### -field FWPS_FIELD_NAME_RESOLUTION_CACHE_V6_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with Windows 7.

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
</table>