---
UID: NE.ucmtypes._UCM_TYPEC_PARTNER
title: UCM_TYPEC_PARTNER
author: windows-driver-content
description: Defines the state of the Type-C connector.
old-location: buses\ucm_type_c_port_state.htm
old-project: usbref
ms.assetid: 4779E943-5C13-4DE2-AF8F-37657F0F99C0
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucmtypes.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
req.alt-api: UCM_TYPEC_PARTNER
req.alt-loc: Ucmtypes.h
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
req.iface: 
req.product: Windows 10 or later.
---

# UCM_TYPEC_PARTNER enumeration



## -description
<p>Defines the state of the Type-C connector.</p>


## -syntax

````
typedef enum _UCM_TYPEC_PARTNER { 
  UcmTypeCPartnerStateInvalid               = 0,
  UcmTypeCPartnerStateUfp ,
  UcmTypeCPartnerStateDfp ,
  UcmTypeCPartnerStatePoweredCableNoUfp ,
  UcmTypeCPartnerStatePoweredCableWithUfp ,
  UcmTypeCPartnerStateAudioAccessory,
  UcmTypeCPartnerStateDebugAccessory
} UCM_TYPEC_PARTNER;
````


## -enum-fields
<dl>

### -field UcmTypeCPartnerStateInvalid 

<dd>
<p>The partner port state is invalid.</p>
</dd>

### -field UcmTypeCPartnerStateUfp 

<dd>
<p>The partner is an Upstream Facing Port (UFP).</p>
</dd>

### -field UcmTypeCPartnerStateDfp 

<dd>
<p>The partner is a Downstream Facing Port (DFP).</p>
</dd>

### -field UcmTypeCPartnerStatePoweredCableNoUfp 

<dd>
<p>The partner is a powered cable that requires VConn, that currently does not have a UFP attached on the other end.</p>
</dd>

### -field UcmTypeCPartnerStatePoweredCableWithUfp 

<dd>
<p>The partner is a powered and upstream facing.</p>
</dd>

### -field UcmTypeCPartnerStateAudioAccessory

<dd>
<p>The partner is used as an audio accessory.</p>
</dd>

### -field UcmTypeCPartnerStateDebugAccessory

<dd>
<p>The partner is a debug accessory.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.15</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.15</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ucmtypes.h (include Ucmcx.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ucmmanager\ns-ucmmanager--ucm-connector-typec-attach-params.md">UCM_CONNECTOR_TYPEC_ATTACH_PARAMS</a>
</dt>
<dt>
<a href="..\ucmmanager\nf-ucmmanager-ucmconnectortypecattach.md">UcmConnectorTypeCAttach</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_TYPEC_PARTNER enumeration%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
