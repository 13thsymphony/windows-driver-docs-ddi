---
UID: NS.wwan._WWAN_CONTEXT_STATE
title: WWAN_CONTEXT_STATE
author: windows-driver-content
description: The WWAN_CONTEXT_STATE structure represents the Packet Data Protocol (PDP) context state of the MB device.
old-location: netvista\wwan_context_state.htm
old-project: netvista
ms.assetid: 0b2a2a94-6c1a-439f-8d54-cc43e79b3b15
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WWAN_CONTEXT_STATE, WWAN_CONTEXT_STATE, *PWWAN_CONTEXT_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WWAN_CONTEXT_STATE
req.alt-loc: wwan.h
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

# WWAN_CONTEXT_STATE structure



## -description
<p>The WWAN_CONTEXT_STATE structure represents the Packet Data Protocol (PDP) context state of the MB
  device.</p>


## -syntax

````
typedef struct _WWAN_CONTEXT_STATE {
  ULONG                 uNwError;
  ULONG                 ConnectionId;
  WWAN_ACTIVATION_STATE ActivationState;
  WWAN_VOICE_CALL_STATE VoiceCallState;
  WWAN_IP_TYPE          IPType;
} WWAN_CONTEXT_STATE, *PWWAN_CONTEXT_STATE;
````


## -struct-fields
<dl>

### -field uNwError

<dd>
<p>A network-specific error. The following table shows the connection failure values as documented in
     the 
     <i>3GPP TS 24.008 Specification</i>.
     </p>
<table>
<tr>
<th>3GPP 24.008 cause code</th>
<th>Interpretation of cause code</th>
</tr>
<tr>
<td>
<p>8 - Operator determined barring</p>
</td>
<td>
<p>Packet data service is blocked by the operator.</p>
</td>
</tr>
<tr>
<td>
<p>26 - Insufficient resources</p>
</td>
<td>
<p>Context cannot be activated because of insufficient resources on network.</p>
</td>
</tr>
<tr>
<td>
<p>27 - Missing or unknown Access Point Name (APN)</p>
</td>
<td>
<p>No APN or unknown APN is provided in the activation request.</p>
</td>
</tr>
<tr>
<td>
<p>29 , 30, 31 - User authentication failed</p>
</td>
<td>
<p>Wrong user name or password provided in the activation request.</p>
</td>
</tr>
<tr>
<td>
<p>32 - Service option not supported</p>
</td>
<td>
<p>GPRS is not supported by the network.</p>
</td>
</tr>
<tr>
<td>
<p>33 - Requested service option is not subscribed</p>
</td>
<td>
<p>Requested service (GPRS) is not subscribed by the user.</p>
</td>
</tr>
<tr>
<td>
<p>34 - Service option is temporarily out of order</p>
</td>
<td>
<p>Packet data service is temporarily out of order. User must retry later.</p>
</td>
</tr>
<tr>
<td>
<p>43 - Unknown Packet Data Protocol (PDP) context</p>
</td>
<td>
<p>No APN or unknown APN is provided in the activation request.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field ConnectionId

<dd>
<p>The MB Service specifies a value for this member at the time of the connect request by using
     OID_WWAN_CONNECT. Miniport drivers must copy this value and use it when they notify the MB Service on
     subsequent connection state changes.</p>
</dd>

### -field ActivationState

<dd>
<p>The current activation state of the device.</p>
</dd>

### -field VoiceCallState

<dd>
<p>The current voice call state of the device.</p>
</dd>

### -field IPType

<dd>
<p>A value from the WWAN_IP_TYPE enumeration that specifies the type of IP.</p>
</dd>
</dl>

## -remarks
<p><i>Set</i> OID requests as well as unsolicited status events use the 
    <b>uNwError</b> member. If there is no network specific error or the network specific error is not known,
    miniport drivers should set this member to 0.</p>

<p>The following points provide guidelines on returning network specific error in different
    scenarios:</p>

<p>If a set request fails, miniport drivers should return the network specific error code. In this
      case, the miniport driver should set the 
      <b>uStatus</b> member of the NDIS_WWAN_CONTEXT_STATE structure to WWAN_STATUS_FAILURE, or a more
      specific error like WWAN_STAUS_INVALID_ACCESS_STRING or WWAN_STATUS_INVALID_USER_NAME_PWD, and set the 
      <b>uNwError</b> member to the network specific error code.</p>

<p>Whenever the device context activation state changes because of network initiated context deactivate
      then unsolicited status events should include the network specific error. In this case, the miniport
      driver should set the 
      <b>uStatus</b> member of the NDIS_WWAN_CONTEXT_STATE structure to WWAN_STATUS_SUCCESS, and set the 
      <b>uNwError</b> member to the network specific error code.</p>

<p>Miniport drivers can provide additional error codes as defined by the GSM standards specification of
    context activation error codes returned by the network. For example, miniport drivers can communicate the
    3GPP specification TS 24.008 context activation error codes, such as error code 8 (Operator determined
    barring), to the MB Service through the 
    <b>uNwError</b> member. There is no standard available for CDMA-based network specific error codes.
    CDMA-based devices and networks can return network specific error code information using the 
    <b>uNwError</b> member.</p>

<p>In case of response to the NDIS_WWAN_SET_CONTEXT_STATE, use this member to provide additional error
    codes returned by the network.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 8 and later versions of Windows.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wwan.h (include Wwan.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wwan\ne-wwan--wwan-activation-state.md">WWAN_ACTIVATION_STATE</a>
</dt>
<dt>
<a href="..\wwan\ne-wwan--wwan-voice-call-state.md">WWAN_VOICE_CALL_STATE</a>
</dt>
<dt>
<a href="..\ndiswwan\ns-ndiswwan--ndis-wwan-context-state.md">NDIS_WWAN_CONTEXT_STATE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_CONTEXT_STATE structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
