---
UID: NE.fwpsk.FWPS_FIELDS_IPSEC_KM_DEMUX_V4_
title: FWPS_FIELDS_IPSEC_KM_DEMUX_V4_
author: windows-driver-content
description: The FWPS_FIELDS_IPSEC_KM_DEMUX_V4 enumeration type specifies the data field identifiers for the FWPS_LAYER_IPSEC_KM_DEMUX_V4 run-time filtering layer.
old-location: netvista\fwps_fields_ipsec_km_demux_v4.htm
old-project: netvista
ms.assetid: b8b95aad-7c55-475a-85d9-6a64434d8a5f
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: FWPS_FIELDS_IPSEC_KM_DEMUX_V4_, FWPS_FIELDS_IPSEC_KM_DEMUX_V4
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Unless otherwise noted, supported starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FWPS_FIELDS_IPSEC_KM_DEMUX_V4
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

# FWPS_FIELDS_IPSEC_KM_DEMUX_V4_ enumeration



## -description
The FWPS_FIELDS_IPSEC_KM_DEMUX_V4 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_IPSEC_KM_DEMUX_V4 
  <a href="netvista.run_time_filtering_layer_identifiers">run-time filtering layer</a>.


## -syntax

````
typedef enum FWPS_FIELDS_IPSEC_KM_DEMUX_V4_ { 
  FWPS_FIELD_IPSEC_KM_DEMUX_V4_IP_LOCAL_ADDRESS,
  FWPS_FIELD_IPSEC_KM_DEMUX_V4_IP_REMOTE_ADDRESS,
#if (NTDDI_VERSION >= NTDDI_WIN8)
  FWPS_FIELD_IPSEC_KM_DEMUX_V4_QM_MODE,
  FWPS_FIELD_IPSEC_KM_DEMUX_V4_IP_LOCAL_INTERFACE,
  FWPS_FIELD_IPSEC_KM_DEMUX_V4_CURRENT_PROFILE_ID,
#endif 
  FWPS_FIELD_IPSEC_KM_DEMUX_V4_MAX
} FWPS_FIELDS_IPSEC_KM_DEMUX_V4;
````


## -enum-fields

### -field FWPS_FIELD_IPSEC_KM_DEMUX_V4_IP_LOCAL_ADDRESS

The local IP address.

### -field FWPS_FIELD_IPSEC_KM_DEMUX_V4_IP_REMOTE_ADDRESS

The remote IP address.

### -field FWPS_FIELD_IPSEC_KM_DEMUX_V4_QM_MODE

The quick mode (QM) mode.
     
<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_FIELD_IPSEC_KM_DEMUX_V4_IP_LOCAL_INTERFACE

The IP local interface.
     
<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_FIELD_IPSEC_KM_DEMUX_V4_CURRENT_PROFILE_ID

The profile identifier (network category) of the network interface. The possible network category values are: public (1), private (2), or domain (3). 


<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_FIELD_IPSEC_KM_DEMUX_V4_MAX

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
Unless otherwise noted, supported starting with Windows Vista.
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