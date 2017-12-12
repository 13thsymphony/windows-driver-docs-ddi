---
UID: NS.BTHDDI._BRB_L2CA_OPEN_CHANNEL
title: _BRB_L2CA_OPEN_CHANNEL
author: windows-driver-content
description: The _BRB_L2CA_OPEN_CHANNEL structure describes a L2CAP channel to open to a remote device, or a response from the profile driver accepting or rejecting an incoming L2CAP connection request that was initiated by a remote device.
old-location: bltooth\_brb_l2ca_open_channel.htm
old-project: bltooth
ms.assetid: 16f79360-c8fd-4be9-9c94-7fa2a1d8c6b5
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _BRB_L2CA_OPEN_CHANNEL,
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
req.alt-api: _BRB_L2CA_OPEN_CHANNEL
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

# _BRB_L2CA_OPEN_CHANNEL structure



## -description
The _BRB_L2CA_OPEN_CHANNEL structure describes a L2CAP channel to open to a remote device, or a
  response from the profile driver accepting or rejecting an incoming L2CAP connection request that was
  initiated by a remote device.



## -syntax

````
struct _BRB_L2CA_OPEN_CHANNEL {
  BRB_HEADER                     Hdr;
  L2CAP_CHANNEL_HANDLE           ChannelHandle;
  union {
    struct {
      USHORT Response;
      USHORT ResponseStatus;
    };
    USHORT Psm;
  };
  ULONG                          ChannelFlags;
  BTH_ADDR                       BtAddress;
  struct {
    ULONG                    Flags;
    L2CAP_CONFIG_VALUE_RANGE Mtu;
    L2CAP_CONFIG_VALUE_RANGE FlushTO;
    L2CAP_FLOWSPEC           Flow;
    USHORT                   LinkTO;
    ULONG                    NumExtraOptions;
    PL2CAP_CONFIG_OPTION     ExtraOptions;
    struct {
      UCHAR ServiceType;
      ULONG Latency;
    } LocalQos;
  } ConfigOut;
  struct {
    ULONG                    Flags;
    L2CAP_CONFIG_VALUE_RANGE Mtu;
    L2CAP_CONFIG_RANGE       FlushTO;
  } ConfigIn;
  ULONG                          CallbackFlags;
  PFNBTHPORT_INDICATION_CALLBACK Callback;
  PVOID                          CallbackContext;
  PVOID                          ReferenceObject;
  CHANNEL_CONFIG_RESULTS         OutResults;
  CHANNEL_CONFIG_RESULTS         InResults;
  UCHAR                          IncomingQueueDepth;
};
````


## -struct-fields

### -field Hdr

A 
     <a href="bltooth.brb_header">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field ChannelHandle


### -field For a BRB_L2CA_OPEN_CHANNEL request, this member will contain a handle to identify the L2CAP
     channel, if the open channel request completes successfully.

### -field For a BRB_L2CA_OPEN_CHANNEL_RESPONSE request, the profile driver (acting as a server) provides
     this member's value prior to sending the BRB down the driver stack. This member's value should be set to
     <a href="bltooth.indication_parameters">INDICATION_PARAMETERS</a> structure's 
     <b>ConnectionHandle</b> member value if the 
     <a href="bltooth.indication_code">INDICATION_CODE</a> enumeration's 
     <b>IndicationRemoteConnect</b> value is specified. These values are passed as the 
     <i>Parameters</i> and 
     <i>Indication</i> arguments of the profile driver's 
     <a href="..\bthddi\nc-bthddi-pfnbthport_indication_callback.md">L2CAP Callback Function</a> that was
     registered as the 
     <b>IndicationCallback</b> member when the profile driver built and sent a 
     <a href="bltooth.brb_l2ca_register_server">
     BRB_L2CA_REGISTER_SERVER</a> request.

</dl>

### -field ( unnamed struct )

A 
      <a href="bltooth.brb_header">BRB_HEADER</a> structure that contains information
      about the current BRB.


### -field Response

This member is used as an input parameter for a <b>BRB_L2CA_OPEN_CHANNEL_RESPONSE</b> request and an
       output parameter for the <b>BRB_L2CA_OPEN_CHANNEL</b> request.
       

For a <b>BRB_L2CA_OPEN_CHANNEL_RESPONSE</b> request, this member holds a flag that indicates the profile
       driver's response to the remote device. Valid flag values are contained in the following table.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
CONNECT_RSP_RESULT_NO_RESOURCES

</td>
<td>
The profile driver refused the connection due to a lack of resources.

</td>
</tr>
<tr>
<td>
CONNECT_RSP_RESULT_PENDING

</td>
<td>
The profile driver is currently busy and cannot accept the connection. Try again later.

</td>
</tr>
<tr>
<td>
CONNECT_RSP_RESULT_PSM_NEG

</td>
<td>
The profile driver refused the connection because the PSM is not supported.

</td>
</tr>
<tr>
<td>
CONNECT_RSP_RESULT_SECURITY_BLOCK

</td>
<td>
The profile driver refused the connection for security reasons.

</td>
</tr>
<tr>
<td>
CONNECT_RSP_RESULT_SUCCESS

</td>
<td>
The profile driver accepted the connection.

</td>
</tr>
</table>
 

For the <b>BRB_L2CA_OPEN_CHANNEL</b> BRB, this member contains the response from the remote device to
       which the profile driver attempted to connect. Valid flag values are contained in the following
       table.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
CONNECT_RSP_RESULT_NO_RESOURCES

</td>
<td>
The remote device refused the connection due to a lack of resources.

</td>
</tr>
<tr>
<td>
CONNECT_RSP_RESULT_PSM_NEG

</td>
<td>
The remote device refused the connection.

</td>
</tr>
<tr>
<td>
CONNECT_RSP_RESULT_SECURITY_BLOCK

</td>
<td>
The remote device refused the connection for security reasons.

</td>
</tr>
<tr>
<td>
CONNECT_RSP_RESULT_SUCCESS

</td>
<td>
The remote device accepted the connection.

</td>
</tr>
</table>
 


### -field ResponseStatus


### -field If during a call to the BRB_L2CA_OPEN_CHANNEL_RESPONSE BRB the 
       <b>Response</b> member is set to CONNECT_RSP_RESULT_PENDING, this member is valid and contains one of
       

### -field CONNECT_RSP_STATUS_AUTHENTICATION_PENDING
       

### -field CONNECT_RSP_STATUS_AUTHORIZATION_PENDING
       

### -field CONNECT_RSP_STATUS_NO_INFORMATION

</dd>
</dl>

### -field Psm

The Protocol/Service Multiplexer (PSM) that the channel uses to connect to the remote device.
      When used with a <b>BRB_L2CA_OPEN_CHANNEL</b> request, this member is set as an input field. When used with a
      <b>BRB_L2CA_OPEN_CHANNEL_RESPONSE</b> request, this member is used as an output field.


### -field ChannelFlags

Flags that specify the requirements for the channel to be opened. Valid flag values are listed in
     the following table:
     

<table>
<tr>
<td>
<b>Flag</b>

</td>
<td>
<b>Description</b>

</td>
</tr>
<tr>
<td>
CF_LINK_AUTHENTICATED

</td>
<td>
The link must be authenticated.

</td>
</tr>
<tr>
<td>
CF_LINK_ENCRYPTED

</td>
<td>
The link must be encrypted. Setting this flag also sets the CF_LINK_AUTHENTICATED flag.

</td>
</tr>
<tr>
<td>
CF_LINK_SUPPRESS_PIN

</td>
<td>
The profile driver indicates its preference that users not be prompted for a PIN.

</td>
</tr>
</table>
 


### -field BtAddress

The Bluetooth address of the device for which the connection is intended.


### -field ConfigOut

The substructure that contains parameter settings for a <b>BRB_L2CA_OPEN_CHANNEL</b> BRB sent to a remote
     device.


### -field Flags

Flags that specify the requirements for the channel to be opened. Valid flag values are listed in
      the following table:
      

<table>
<tr>
<td>
<b>Flag</b>

</td>
<td>
<b>Description</b>

</td>
</tr>
<tr>
<td>
CF_LINK_AUTHENTICATED

</td>
<td>
The link must be authenticated.

</td>
</tr>
<tr>
<td>
CF_LINK_ENCRYPTED

</td>
<td>
The link must be encrypted. Setting this flag also sets the CF_LINK_AUTHENTICATED flag.

</td>
</tr>
<tr>
<td>
CF_LINK_SUPPRESS_PIN

</td>
<td>
The profile driver indicates its preference that users not be prompted for a PIN.

</td>
</tr>
</table>
 


### -field Mtu

The range of message transfer units (MTUs) that is used to negotiate the size of the outbound
      half of channel.


### -field FlushTO

The range of possible values to be used for the flush timeout for the outbound half of the
      channel.


### -field Flow

Reserved for future use. Do not use.


### -field LinkTO

The Link Manager link timeout.


### -field NumExtraOptions

The number of array items that are contained in the 
      <b>ExtraOptions</b> member. This value should be zero for most clients.


### -field ExtraOptions

The number of array items that are contained in the 
      <b>ExtraOptions</b> member. This value should be zero for most clients.


### -field LocalQos

Reserved for future use. Do not use.


### -field ServiceType

Reserved for future use. Do not use.


### -field Latency

Reserved for future use. Do not use.

</dd>
</dl>
</dd>
</dl>

### -field ConfigIn

The substructure that contains parameter settings to validate incoming
     <b>BRB_L2CA_OPEN_CHANNEL_RESPONSE</b> BRBs that are sent from a remote device.


### -field Flags

Flags that specify the requirements for the channel to be opened. Valid flag values are listed in
      the following table:
      

<table>
<tr>
<td>
<b>Flag</b>

</td>
<td>
<b>Description</b>

</td>
</tr>
<tr>
<td>
CF_LINK_AUTHENTICATED

</td>
<td>
The link must be authenticated.

</td>
</tr>
<tr>
<td>
CF_LINK_ENCRYPTED

</td>
<td>
The link must be encrypted. Setting this flag also sets the CF_LINK_AUTHENTICATED flag.

</td>
</tr>
<tr>
<td>
CF_LINK_SUPPRESS_PIN

</td>
<td>
The profile driver indicates its preference that users not be prompted for a PIN.

</td>
</tr>
</table>
 


### -field Mtu

The range of message transfer units (MTUs) that is used to negotiate the size of the outbound
      half of channel.


### -field FlushTO

The range of possible values to be used for the flush timeout for the outbound half of the
      channel.

</dd>
</dl>

### -field CallbackFlags

A flag that specifies which events should generate a callback routine to notify the profile driver
     that the event has occurred. Valid flag values are contained in the following table.
     

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
CALLBACK_CONFIG_EXTRA_IN

</td>
<td>
If set, the callback routine will be called when the configuration request for the remote device
        contains extra options. If not set, the extra configuration options will be rejected as unknown
        options. This flag is used with <b>BRB_L2CA_OPEN_CHANNEL_RESPONSE</b> BRBs.

</td>
</tr>
<tr>
<td>
CALLBACK_CONFIG_EXTRA_OUT

</td>
<td>
If set, the callback routine will be called when the remote device rejects an extra configuration
        option from a <b>BRB_L2CA_OPEN_CHANNEL</b> request. If not set and the remote device rejects the
        configuration request due to an extra option, the connection will be closed.

</td>
</tr>
<tr>
<td>
CALLBACK_CONFIG_QOS

</td>
<td>
If set, the callback routine will be called when a remote device sends a configuration request
        that contains a QOS value. If this flag is not set and the remote device either sends QOS parameters
        in a configuration request or rejects the profile driver's requested QOS parameters, the connection
        is disconnected.

</td>
</tr>
<tr>
<td>
CALLBACK_DISCONNECT

</td>
<td>
If set, the callback routine will be called when a remote device disconnects from the L2CAP
        channel.

</td>
</tr>
<tr>
<td>
CALLBACK_RECV_PACKET

</td>
<td>
If set, the callback routine will be called when the profile driver receives an incoming L2CAP
        packet.

</td>
</tr>
</table>
 


### -field Callback

The 
     <a href="..\bthddi\nc-bthddi-pfnbthport_indication_callback.md">L2CAP Callback
     Function</a> implemented by the profile driver, that the Bluetooth driver stack should call to notify
     the profile driver about any changes to the L2CAP connection.


### -field CallbackContext

The context to pass to the callback function specified in the 
     <b>Callback</b> member. The profile driver defines this value.


### -field ReferenceObject

A pointer to an object to pass to 
     <a href="kernel.obreferenceobject">ObReferenceObject</a> and 
     <a href="kernel.obdereferenceobject">ObDereferenceObject</a> for which to
     maintain a reference count of.


### -field OutResults

A 
     <a href="bltooth.channel_config_results">CHANNEL_CONFIG_RESULTS</a> structure that
     contains configuration parameters for the outbound request.


### -field InResults

A CHANNEL_CONFIG_RESULTS structure that contains configuration parameters for the inbound
     request.


### -field IncomingQueueDepth

Specifies the incoming queue length in message transfer units (MTUs).


## -remarks
To open a L2CAP channel, profile drivers should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536615">BRB_L2CA_OPEN_CHANNEL</a> request.

Profile drivers that act as clients specify a destination address, a PSM, and a variety of
    configuration parameters.

If the <b>BRB_L2CA_OPEN_CHANNEL</b> request completes successfully, a variety of information about the newly
    created connection is available in the 
    <b>OutResults</b> and 
    <b>InResults</b> members. 
    <b>OutResults</b> specifies the parameters for the outbound half of the channel, and 
    <b>InResults</b> specifies the parameters for the inbound half of the channel.

Several of the configuration parameters passed in this structure, such as the 
    <b>Mtu</b> member, are ranges used for negotiation with the remote radio. Clients should provide as wide a
    range as possible to increase the chances of successful channel negotiation. Specifying a minimum MTU
    size greater than the basic Bluetooth minimum MTU size should only be done when absolutely necessary. If
    negotiation fails, the connection will fail.

Profile drivers must allocate the memory to store the array that is stored in the 
    <b>ExtraOptions</b> member and should not free this memory until the callback function defined in the 
    <b>Callback</b> member returns with an 
    <b>IndicationFreeExtraOptions</b> notification 
    <a href="bltooth.indication_code">INDICATION_CODE</a> value passed in its 
    <i>Indication</i> parameter.

The 
    <b>IncomingQueueDepth</b> member of the _BRB_L2CA_OPEN_CHANNEL structure specifies the maximum number of
    MTUs that the Bluetooth driver stack will receive and queue on the connection before it begins to discard
    them. Setting this value to a very small number increases the chances of data loss, while setting it to a
    very large number can increase memory usage. Setting this member to 10 is an effective compromise.

To accept or reject an incoming L2CAP connection request initiated by a remote device, profile drivers
    should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="bltooth.brb_l2ca_open_channel_response">
    BRB_L2CA_OPEN_CHANNEL_RESPONSE</a> request.

A profile driver should build and send a <b>BRB_L2CA_OPEN_CHANNEL_RESPONSE</b> request when the Bluetooth
    driver stack calls the profile driver's 
    <a href="..\bthddi\nc-bthddi-pfnbthport_indication_callback.md">L2CAP Callback Function</a> and passes 
    <b>IndicationRemoteConnect</b> in the callback function's 
    <i>Indication</i> parameter.

Based on the value of the 
    <b>Response</b> member of this structure, the Bluetooth driver stack will then accept or reject the
    connection request.

The profile driver specifies whether the connection should be accepted by storing an appropriate value
    in the 
    <b>Response</b> member of this structure.

Upon receiving the CONNECT_RSP_RESULT_PENDING response, the connecting client should reset its
    connection timer and wait for an updated connection response message. Profile drivers calling the
    <b>BRB_L2CA_OPEN_CHANNEL_RESPONSE</b> BRB where the 
    <b>Response</b> member is set to CONNECT_RSP_RESULT_PENDING should promptly issue an additional
    <b>BRB_L2CA_OPEN_CHANNEL_RESPONSE</b> BRB with an updated connection value. The updated value can be any of the
    status codes described in the 
    <b>Response</b> member, including resending a CONNECT_RSP_RESULT_PENDING value.

Profile drivers must allocate the memory to store the array that is stored in the 
    <b>ExtraOptions</b> member and should not free this memory until the callback function that is defined in
    the 
    <b>Callback</b> member returns with an 
    <b>IndicationFreeExtraOptions</b> notification 
    <b>INDICATION_CODE</b> value passed in its 
    <i>Indication</i> parameter.


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
<a href="bltooth.brb_header">BRB_HEADER</a>
</dt>
<dt>
<a href="bltooth.indication_parameters">INDICATION_PARAMETERS</a>
</dt>
<dt>
<a href="bltooth.indication_code">INDICATION_CODE</a>
</dt>
<dt>
<a href="..\bthddi\nc-bthddi-pfnbthport_indication_callback.md">L2CAP Callback Function</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536618">BRB_L2CA_REGISTER_SERVER</a>
</dt>
<dt>
<a href="bltooth.l2cap_config_option">L2CAP_CONFIG_OPTION</a>
</dt>
<dt>
<a href="kernel.obreferenceobject">ObReferenceObject</a>
</dt>
<dt>
<a href="kernel.obdereferenceobject">ObDereferenceObject</a>
</dt>
<dt>
<a href="bltooth.channel_config_results">CHANNEL_CONFIG_RESULTS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536615">BRB_L2CA_OPEN_CHANNEL</a>
</dt>
<dt>
<a href="bltooth.brb_l2ca_open_channel_response">
   BRB_L2CA_OPEN_CHANNEL_RESPONSE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20_BRB_L2CA_OPEN_CHANNEL structure%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

