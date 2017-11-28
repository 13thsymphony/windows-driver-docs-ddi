---
UID: NE.ucmtypes._UCM_PD_CONN_STATE
title: UCM_PD_CONN_STATE
author: windows-driver-content
description: Defines power delivery (PD) negotiation states of a Type-C port.
old-location: buses\ucm_pd_conn_state.htm
old-project: usbref
ms.assetid: 7D146DDF-58A5-40C2-BF21-AF785DC7DB18
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
req.alt-api: UCM_PD_CONN_STATE
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

# UCM_PD_CONN_STATE enumeration



## -description
<p>Defines power delivery (PD) negotiation states of a Type-C port.</p>


## -syntax

````
typedef enum _UCM_PD_CONN_STATE { 
  UcmPdConnStateInvalid               = 0x0,
  UcmPdConnStateNotSupported,
  UcmPdConnStateNegotiationFailed,
  UcmPdConnStateNegotiationSucceeded
} UCM_PD_CONN_STATE;
````


## -enum-fields
<dl>

### -field <a id="UcmPdConnStateInvalid"></a><a id="ucmpdconnstateinvalid"></a><a id="UCMPDCONNSTATEINVALID"></a><b>UcmPdConnStateInvalid</b>

<dd>
<p>Indicates the PD negotiation state is invalid.</p>
</dd>

### -field <a id="UcmPdConnStateNotSupported"></a><a id="ucmpdconnstatenotsupported"></a><a id="UCMPDCONNSTATENOTSUPPORTED"></a><b>UcmPdConnStateNotSupported</b>

<dd>
<p>Indicates a PD connection is not supported. </p>
</dd>

### -field <a id="UcmPdConnStateNegotiationFailed"></a><a id="ucmpdconnstatenegotiationfailed"></a><a id="UCMPDCONNSTATENEGOTIATIONFAILED"></a><b>UcmPdConnStateNegotiationFailed</b>

<dd>
<p>Indicates the PD negotiation failed.</p>
</dd>

### -field <a id="UcmPdConnStateNegotiationSucceeded"></a><a id="ucmpdconnstatenegotiationsucceeded"></a><a id="UCMPDCONNSTATENEGOTIATIONSUCCEEDED"></a><b>UcmPdConnStateNegotiationSucceeded</b>

<dd>
<p>Indicates the PD negotiation succeeded.</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/mt187911">UcmConnectorPdConnectionStateChanged</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_PD_CONN_STATE enumeration%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
