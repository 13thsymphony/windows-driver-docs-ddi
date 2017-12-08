---
UID: NS.BTHDDI._INDICATION_PARAMETERS~R1
title: _INDICATION_PARAMETERS
author: windows-driver-content
description: The INDICATION_PARAMETERS structure is passed as the Parameters parameter to a profile driver's L2CAP Callback Function.
old-location: bltooth\indication_parameters.htm
old-project: bltooth
ms.assetid: fc93ab8a-01d2-4827-8d89-06f09bf10456
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _INDICATION_PARAMETERS, *PINDICATION_PARAMETERS, INDICATION_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: INDICATION_PARAMETERS
req.alt-loc: bthddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
---

# _INDICATION_PARAMETERS structure



## -description
The INDICATION_PARAMETERS structure is passed as the 
  <i>Parameters</i> parameter to a profile driver's 
  <a href="..\bthddi\nc-bthddi-pfnbthport_indication_callback.md">L2CAP Callback Function</a>.


## -syntax

````
typedef struct _INDICATION_PARAMETERS {
  L2CAP_CHANNEL_HANDLE ConnectionHandle;
  BTH_ADDR             BtAddress;
  union {
    struct {
      struct {
        USHORT PSM;
      } Request;
    } Connect;
    struct {
      CHANNEL_CONFIG_PARAMETERS CurrentParams;
      CHANNEL_CONFIG_PARAMETERS RequestedParams;
      CHANNEL_CONFIG_PARAMETERS ResponseParams;
      USHORT                    Response;
    } ConfigRequest;
    struct {
      CHANNEL_CONFIG_PARAMETERS CurrentParams;
      CHANNEL_CONFIG_PARAMETERS RequestedParams;
      CHANNEL_CONFIG_PARAMETERS RejectedParams;
      PCO_TYPE                  UnknownTypes;
      ULONG                     NumUnknownTypes;
      CHANNEL_CONFIG_PARAMETERS NewRequestParams;
      USHORT                    Response;
    } ConfigResponse;
    struct {
      ULONG                NumExtraOptions;
      PL2CAP_CONFIG_OPTION ExtraOptions;
    } FreeExtraOptions;
    struct {
      L2CAP_DISCONNECT_REASON Reason;
      BOOLEAN                 CloseNow;
    } Disconnect;
    struct {
      ULONG PacketLength;
      ULONG TotalQueueLength;
    } RecvPacket;
  } Parameters;
} INDICATION_PARAMETERS, *PINDICATION_PARAMETERS;
````


## -struct-fields

### -field ConnectionHandle

The L2CAP connection handle to the remote device. This handle is only valid for notifications that
     arrive over an established L2CAP connection.

### -field BtAddress

The Bluetooth address of the remote device.

### -field Parameters


### -field Connect

The structure that contains parameters for the 
      <b>IndicationRemoteConnect</b> callback function.

### -field Request

The structure that contains the parameters for a connection request.

### -field PSM

The Protocol/Service Multiplexer (PSM) that is passed to the calling function when the 
        <b>IndicationRemoteConnectINDICATION_CODE</b> value is specified in the callback function's 
        <i>Indication</i> parameter.
</dd>
</dl>
</dd>
</dl>

### -field ConfigRequest

The structure that contains parameters for the 
      <b>IndicationRemoteConfigRequestINDICATION_CODE</b> value.

### -field CurrentParams

A 
       <a href="bltooth.channel_config_parameters">
       CHANNEL_CONFIG_PARAMETERS</a> structure that contains the parameters for the current channel. This
       value is only valid if the channel was previously open and is now in the process of being configured.
       This member is used when the callback function specifies the 
       <b>IndicationRemoteConfigRequestINDICATION_CODE</b> value.

### -field RequestedParams

A CHANNEL_CONFIG_PARAMETERS structure that contains the parameters that are passed from the
       remote host for configuration requests. This member is used when the callback function specifies the 
       <b>IndicationRemoteConfigRequestINDICATION_CODE</b> value.

### -field ResponseParams

A CHANNEL_CONFIG_PARAMETERS structure that contains the parameters that the profile driver
       responds to the configuration request with.

### -field Response

A flag that indicates the status of the configuration request. Valid flag values are listed in
       the following table.
       
<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
CONFIG_STATUS_SUCCESS
</td>
<td>
The configuration request was successful.
</td>
</tr>
<tr>
<td>
CONFIG_STATUS_DISCONNECT
</td>
<td>
The configuration request failed because the L2CAP connection was disconnected.
</td>
</tr>
<tr>
<td>
CONFIG_STATUS_INVALID_PARAMETER
</td>
<td>
The configuration request failed because an invalid parameter was passed to the profile
          driver.
</td>
</tr>
<tr>
<td>
CONFIG_STATUS_REJECT
</td>
<td>
The profile driver rejected the configuration request.
</td>
</tr>
<tr>
<td>
CONFIG_STATUS_UNKNOWN_OPTION
</td>
<td>
The configuration request failed because one of the specified configuration options was not
          recognized by the profile driver.
</td>
</tr>
</table>
 
</dd>
</dl>

### -field ConfigResponse

The structure that contains parameters for the 
      <b>IndicationRemoteConfigResponseINDICATION_CODE</b> value.

### -field CurrentParams

A 
       <a href="bltooth.channel_config_parameters">
       CHANNEL_CONFIG_PARAMETERS</a> structure that contains the parameters for the current channel. This
       value is only valid if the channel was previously open and is now in the process of being configured.
       This member is used when the callback function specifies the 
       <b>IndicationRemoteConfigRequestINDICATION_CODE</b> value.

### -field RequestedParams

A CHANNEL_CONFIG_PARAMETERS structure that contains the parameters that are passed from the
       remote host for configuration requests. This member is used when the callback function specifies the 
       <b>IndicationRemoteConfigRequestINDICATION_CODE</b> value.

### -field RejectedParams

A CHANNEL_CONFIG_PARAMETERS structure that contains the configuration parameter settings that
       were rejected by the remote device.

### -field UnknownTypes

An array of types that were not recognized by the responding device.

### -field NumUnknownTypes

The number of unrecognized types in the 
       <b>UnknownTypes</b> member.

### -field NewRequestParams

A CHANNEL_CONFIG_PARAMETERS structure that contains the parameter settings for the callback
       function to resubmit after the response has returned from the remote device.

### -field Response

A flag that indicates the status of the configuration request. Valid flag values are listed in
       the following table.
       
<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
CONFIG_STATUS_SUCCESS
</td>
<td>
The configuration request was successful.
</td>
</tr>
<tr>
<td>
CONFIG_STATUS_DISCONNECT
</td>
<td>
The configuration request failed because the L2CAP connection was disconnected.
</td>
</tr>
<tr>
<td>
CONFIG_STATUS_INVALID_PARAMETER
</td>
<td>
The configuration request failed because an invalid parameter was passed to the profile
          driver.
</td>
</tr>
<tr>
<td>
CONFIG_STATUS_REJECT
</td>
<td>
The profile driver rejected the configuration request.
</td>
</tr>
<tr>
<td>
CONFIG_STATUS_UNKNOWN_OPTION
</td>
<td>
The configuration request failed because one of the specified configuration options was not
          recognized by the profile driver.
</td>
</tr>
</table>
 
</dd>
</dl>

### -field FreeExtraOptions

The structure that contains parameters for the 
      <b>IndicationFreeExtraOptionsINDICATION_CODE</b> value.

### -field NumExtraOptions

The number of extra options contained in the 
       <b>ExtraOptions</b> member.

### -field ExtraOptions

The number of extra options contained in the 
       <b>ExtraOptions</b> member.
</dd>
</dl>

### -field Disconnect

The structure that contains the parameters for the 
      <b>IndicationRemoteDisconnectINDICATION_CODE</b> value.

### -field Reason

An 
       <a href="bltooth.l2cap_disconnect_reason">L2CAP_DISCONNECT_REASON</a> value that
       indicates why the L2CAP connection to the remote device was terminated.

### -field CloseNow

A Boolean value that a profile driver uses to notify the Bluetooth driver stack to close the
       L2CAP connection. Set this member to <b>TRUE</b> to notify the Bluetooth driver stack to close the
       connection. Otherwise, set it to <b>FALSE</b> to keep the connection open.
</dd>
</dl>

### -field RecvPacket

The structure that contains the parameters for the 
      <b>IndicationRecvPacketINDICATION_CODE</b> value.

### -field PacketLength

The size, in bytes, of the packet that the callback function sent over the L2CAP
       connection.

### -field TotalQueueLength

The number of packets to be processed over the L2CAP connection.
</dd>
</dl>
</dd>
</dl>

## -remarks
A profile driver's 
    <a href="..\bthddi\nc-bthddi-pfnbthport_indication_callback.md">L2CAP Callback Function</a> should
    process this structure differently depending upon the value that the Bluetooth driver stack passes in the
    
    <i>Indication</i> parameter of the callback function.

When the Bluetooth driver stack passes 
    <b>IndicationRemoteConnect</b>, the callback function should use the 
    <b>Connect</b> member of the 
    <b>Parameters</b> union.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Versions: Supported in Windows Vista, and later.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Bthddi.h (include Bthddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\bthddi\nc-bthddi-pfnbthport_indication_callback.md">L2CAP Callback Function</a>
</dt>
<dt>
<a href="bltooth.channel_config_parameters">CHANNEL_CONFIG_PARAMETERS</a>
</dt>
<dt>
<a href="bltooth.l2cap_config_option">L2CAP_CONFIG_OPTION</a>
</dt>
<dt>
<a href="bltooth.l2cap_disconnect_reason">L2CAP_DISCONNECT_REASON</a>
</dt>
<dt>
<a href="bltooth.indication_code">INDICATION_CODE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20INDICATION_PARAMETERS structure%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
