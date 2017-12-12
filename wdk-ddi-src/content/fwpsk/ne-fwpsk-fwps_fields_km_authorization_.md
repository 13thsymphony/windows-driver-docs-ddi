---
UID: NE.fwpsk.FWPS_FIELDS_KM_AUTHORIZATION_
title: FWPS_FIELDS_KM_AUTHORIZATION_
author: windows-driver-content
description: The FWPS_FIELDS_KM_AUTHORIZATION enumeration type specifies the data field identifiers for the FWPS_LAYER_KM_AUTHORIZATION run-time filtering layer.
old-location: netvista\fwps_fields_km_authorization.htm
old-project: netvista
ms.assetid: c15ed590-4a7f-4f21-8e6e-1440a57b5659
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: FWPS_FIELDS_KM_AUTHORIZATION_, FWPS_FIELDS_KM_AUTHORIZATION
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
req.alt-api: FWPS_FIELDS_KM_AUTHORIZATION
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

# FWPS_FIELDS_KM_AUTHORIZATION_ enumeration



## -description
The FWPS_FIELDS_KM_AUTHORIZATION enumeration type specifies the data field identifiers for the
  FWPS_LAYER_KM_AUTHORIZATION 
  <a href="netvista.run_time_filtering_layer_identifiers">run-time filtering layer</a>.



## -syntax

````
typedef enum FWPS_FIELDS_KM_AUTHORIZATION_ { 
  FWPS_FIELD_KM_AUTHORIZATION_REMOTE_ID,
  FWPS_FIELD_KM_AUTHORIZATION_AUTHENTICATION_TYPE,
  FWPS_FIELD_KM_AUTHORIZATION_KM_TYPE,
  FWPS_FIELD_KM_AUTHORIZATION_DIRECTION,
  FWPS_FIELD_KM_AUTHORIZATION_KM_MODE,
  FWPS_FIELD_KM_AUTHORIZATION_IPSEC_POLICY_KEY,
  FWPS_FIELD_KM_AUTHORIZATION_NAP_CONTEXT,
  FWPS_FIELD_KM_AUTHORIZATION_MAX
} FWPS_FIELDS_KM_AUTHORIZATION;
````


## -enum-fields

### -field FWPS_FIELD_KM_AUTHORIZATION_REMOTE_ID

The peer's identifier. This can be the User or Machine Token depending on the type, auth type, and
     mode.


### -field FWPS_FIELD_KM_AUTHORIZATION_AUTHENTICATION_TYPE

The type of authentication used.


### -field FWPS_FIELD_KM_AUTHORIZATION_KM_TYPE

The type of Keying Module (KM) used.


### -field FWPS_FIELD_KM_AUTHORIZATION_DIRECTION


### -field The direction of the data flow. The possible values are:
     

### -field FWP_DIRECTION_INBOUND
     

### -field FWP_DIRECTION_OUTBOUND


### -field FWPS_FIELD_KM_AUTHORIZATION_KM_MODE

The authorization mode.


### -field FWPS_FIELD_KM_AUTHORIZATION_IPSEC_POLICY_KEY

The associated IPsec policy key.


### -field FWPS_FIELD_KM_AUTHORIZATION_NAP_CONTEXT

The Network Access Protection (NAP) certificate context.


### -field FWPS_FIELD_KM_AUTHORIZATION_MAX

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