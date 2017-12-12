---
UID: NS.BTHDDI._BRB_SCO_GET_CHANNEL_INFO
title: _BRB_SCO_GET_CHANNEL_INFO
author: windows-driver-content
description: The _BRB_SCO_GET_CHANNEL_INFO structure describes the settings and statistics of a SCO channel.
old-location: bltooth\_brb_sco_get_channel_info.htm
old-project: bltooth
ms.assetid: 1a7eb79c-5a3e-4977-ba1f-682bbebb0494
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _BRB_SCO_GET_CHANNEL_INFO,
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
req.alt-api: _BRB_SCO_GET_CHANNEL_INFO
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

# _BRB_SCO_GET_CHANNEL_INFO structure



## -description
The _BRB_SCO_GET_CHANNEL_INFO structure describes the settings and statistics of a SCO
  channel.



## -syntax

````
struct _BRB_SCO_GET_CHANNEL_INFO {
  BRB_HEADER                Hdr;
  BTH_ADDR                  BtAddress;
  SCO_CHANNEL_HANDLE        ChannelHandle;
  ULONG                     InfoFlags;
  ULONG                     TransmitBandwidth;
  ULONG                     ReceiveBandwidth;
  USHORT                    MaxLatency;
  USHORT                    PacketType;
  USHORT                    ContentFormat;
  USHORT                    Reserved;
  SCO_RETRANSMISSION_EFFORT RetransmissionEffort;
  ULONG                     ChannelFlags;
  CONNECTION_HANDLE         HciConnectionHandle;
  SCO_LINK_TYPE             LinkType;
  BASEBAND_CHANNEL_INFO     BasebandInfo;
};
````


## -struct-fields

### -field Hdr

A 
     <a href="bltooth.brb_header">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field BtAddress

The Bluetooth address of the remote device.


### -field ChannelHandle

The handle to the SCO channel to query.


### -field InfoFlags

A flag that determines if baseband information is available for the SCO channel. The following
     flag is defined:
     

<table>
<tr>
<th>
       Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
SCO_INFO_BASEBAND_AVAILABLE

</td>
<td>
If set, baseband settings are available for the SCO channel.

</td>
</tr>
</table>
 


### -field TransmitBandwidth

The transmission bandwidth of the channel, in bytes per second.


### -field ReceiveBandwidth

The reception bandwidth of the channel, in bytes per second.


### -field MaxLatency

A value that represents the upper limit of the sum of the synchronous interval and the size of the
     SCO window, in milliseconds. Possible values are listed in the following table.
     

<table>
<tr>
<th>
       Values</th>
<th>Description</th>
</tr>
<tr>
<td>
0x0000 to 0x0003

</td>
<td>
Reserved for future use.

</td>
</tr>
<tr>
<td>
0x0004 to 0xFFFE

</td>
<td>
The range of latency values for the channel.

</td>
</tr>
<tr>
<td>
0xFFFF

</td>
<td>
The channel doesn't have a preferred 
        <b>MaxLatency</b> setting.

</td>
</tr>
</table>
 


### -field PacketType

A flag or combination of flags that indicates the type of data packets that the SCO channel
     supports. These SCO packet types are defined by the Bluetooth SIG. See the Bluetooth specification for
     more information about these flags. Possible values include:
     



### -field SCO_HV1
     

### -field SCO_HV2
     

### -field SCO_HV3
     

### -field SCO_EV3
     

### -field SCO_EV4
     

### -field SCO_EV5




### -field ContentFormat

The audio voice setting for the channel. Use the following definitions to decode this member:
     



### -field SCO_VS_AIR_CODING_DATA
     

### -field SCO_VS_AIR_CODING_FORMAT_ALAW
     

### -field SCO_VS_AIR_CODING_FORMAT_CVSD
     

### -field SCO_VS_AIR_CODING_FORMAT_MASK
     

### -field SCO_VS_AIR_CODING_FORMAT_MULAW
     

### -field SCO_VS_IN_CODING_ALAW
     

### -field SCO_VS_IN_CODING_LINEAR
     

### -field SCO_VS_IN_CODING_MASK
     

### -field SCO_VS_IN_CODING_MULAW
     

### -field SCO_VS_IN_DATA_FORMAT_1C
     

### -field SCO_VS_IN_DATA_FORMAT_2C
     

### -field SCO_VS_IN_DATA_FORMAT_MASK
     

### -field SCO_VS_IN_DATA_FORMAT_SM
     

### -field SCO_VS_IN_DATA_FORMAT_US
     

### -field SCO_VS_IN_SAMPLE_SIZE_8BIT
     

### -field SCO_VS_IN_SAMPLE_SIZE_16BIT
     

### -field SCO_VS_IN_SAMPLE_SIZE_MASK
     

### -field SCO_VS_PCM_BIT_POS_MASK
     

### -field SCO_VS_SETTING_DEFAULT




### -field Reserved

Reserved for future use. Do not use.


### -field RetransmissionEffort

A 
     <a href="bltooth.sco_retransmission_effort">SCO_RETRANSMISSION_EFFORT</a> value that
     determines the channel's retransmission policies.


### -field ChannelFlags

Flags that specify how the channel was opened. Valid flag values are listed in the following
     table.
     

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
SCO_CF_LINK_AUTHENTICATED

</td>
<td>
The link must be authenticated.

</td>
</tr>
<tr>
<td>
SCO_CF_LINK_ENCRYPTED

</td>
<td>
The link must be encrypted. Setting this flag also sets the SCO_CF_LINK_AUTHENTICATED flag.

</td>
</tr>
<tr>
<td>
SCO_CF_LINK_SUPPRESS_PIN

</td>
<td>
The profile driver indicates its preference that users not be prompted for a PIN.

</td>
</tr>
</table>
 


### -field HciConnectionHandle

The host controller interface's connection handle for the SCO connection.


### -field LinkType

The 
     <a href="bltooth.sco_link_type">SCO_LINK_TYPE</a> that is associated with the host
     controller interface.


### -field BasebandInfo

A 
     <a href="bltooth.baseband_channel_info">BASEBAND_CHANNEL_INFO</a> structure that
     contains information for the SCO connection. This information is only available for links established
     using the 1.2 Bluetooth Synchronous Commands.


## -remarks
To get the settings and statistics of a SCO channel, profile drivers should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="bltooth.brb_sco_get_channel_info">
    BRB_SCO_GET_CHANNEL_INFO</a> request.


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
<a href="bltooth.sco_retransmission_effort">SCO_RETRANSMISSION_EFFORT</a>
</dt>
<dt>
<a href="bltooth.sco_link_type">SCO_LINK_TYPE</a>
</dt>
<dt>
<a href="bltooth.baseband_channel_info">BASEBAND_CHANNEL_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536624">BRB_SCO_GET_CHANNEL_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20_BRB_SCO_GET_CHANNEL_INFO structure%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

