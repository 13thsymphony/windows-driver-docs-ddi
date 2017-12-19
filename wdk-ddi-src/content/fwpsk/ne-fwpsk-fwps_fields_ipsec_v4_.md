---
UID: NE.fwpsk.FWPS_FIELDS_IPSEC_V4_
title: FWPS_FIELDS_IPSEC_V4_
author: windows-driver-content
description: The FWPS_FIELDS_IPSEC_V4 enumeration type specifies the data field identifiers for the FWPS_LAYER_IPSEC_V4 run-time filtering layer.
old-location: netvista\fwps_fields_ipsec_v4.htm
old-project: NetVista
ms.assetid: 6477bc7f-60b0-4d3c-b8a2-f7d950f60fd2
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FWPS_FIELDS_IPSEC_V4_, FWPS_FIELDS_IPSEC_V4
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
req.alt-api: FWPS_FIELDS_IPSEC_V4
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

# FWPS_FIELDS_IPSEC_V4_ enumeration



## -description
The FWPS_FIELDS_IPSEC_V4 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_IPSEC_V4 
  <a href="netvista.run_time_filtering_layer_identifiers">run-time filtering layer</a>.



## -syntax

````
typedef enum FWPS_FIELDS_IPSEC_V4_ { 
  FWPS_FIELD_IPSEC_V4_IP_PROTOCOL,
  FWPS_FIELD_IPSEC_V4_IP_LOCAL_ADDRESS,
  FWPS_FIELD_IPSEC_V4_IP_REMOTE_ADDRESS,
  FWPS_FIELD_IPSEC_V4_IP_LOCAL_PORT,
  FWPS_FIELD_IPSEC_V4_IP_REMOTE_PORT,
  FWPS_FIELD_IPSEC_V4_IP_LOCAL_INTERFACE,
#if (NTDDI_VERSION >= NTDDI_WIN7)
  FWPS_FIELD_IPSEC_V4_PROFILE_ID,
#endif 
  FWPS_FIELD_IPSEC_V4_MAX
} FWPS_FIELDS_IPSEC_V4;
````


## -enum-fields

### -field FWPS_FIELD_IPSEC_V4_IP_PROTOCOL

The IP protocol number, as specified in RFC 1700.


### -field FWPS_FIELD_IPSEC_V4_IP_LOCAL_ADDRESS

The local IP address.


### -field FWPS_FIELD_IPSEC_V4_IP_REMOTE_ADDRESS

The remote IP address.


### -field FWPS_FIELD_IPSEC_V4_IP_LOCAL_PORT

The local transport protocol port number.


### -field FWPS_FIELD_IPSEC_V4_IP_REMOTE_PORT

The remote transport protocol port number.


### -field FWPS_FIELD_IPSEC_V4_IP_LOCAL_INTERFACE

The locally unique identifier (<a href="netvista.luid">LUID</a>) for the network interface associated with the
     local IP address.


### -field FWPS_FIELD_IPSEC_V4_PROFILE_ID

The profile identifier (network category) of the network interface. The possible network category
     values are: public (1), private (2), or domain (3).
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_IPSEC_V4_MAX

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