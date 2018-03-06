---
UID: NS:bthddi._BRB_SCO_OPEN_CHANNEL
title: "_BRB_SCO_OPEN_CHANNEL"
author: windows-driver-content
description: The _BRB_SCO_OPEN_CHANNEL structure describes a SCO channel to open to a remote device, or a response from the profile driver accepting or rejecting an incoming SCO connection request that was initiated by a remote device.
old-location: bltooth\_brb_sco_open_channel.htm
old-project: bltooth
ms.assetid: 7f73aaec-09fb-45f2-bff0-daef9fdb9b90
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "_BRB_SCO_OPEN_CHANNEL, _BRB_SCO_OPEN_CHANNEL structure [Bluetooth Devices], bltooth._brb_sco_open_channel, bth_structs_f852010d-7117-48fe-bd65-f4e4f17e8706.xml, bthddi/_BRB_SCO_OPEN_CHANNEL"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	_BRB_SCO_OPEN_CHANNEL
product: Windows
targetos: Windows
req.typenames: 
---

# _BRB_SCO_OPEN_CHANNEL structure
The _BRB_SCO_OPEN_CHANNEL structure describes a SCO channel to open to a remote device, or a response
  from the profile driver accepting or rejecting an incoming SCO connection request that was initiated by a
  remote device.

## Syntax
````
struct _BRB_SCO_OPEN_CHANNEL {
  BRB_HEADER                 Hdr;
  BTH_ADDR                   BtAddress;
  ULONG                      TransmitBandwidth;
  ULONG                      ReceiveBandwidth;
  USHORT                     MaxLatency;
  USHORT                     PacketType;
  USHORT                     ContentFormat;
  USHORT                     Reserved;
  SCO_RETRANSMISSION_EFFORT  RetransmissionEffort;
  ULONG                      ChannelFlags;
  ULONG                      CallbackFlags;
  PFNSCO_INDICATION_CALLBACK Callback;
  PVOID                      CallbackContext;
  PVOID                      ReferenceObject;
  SCO_CHANNEL_HANDLE         ChannelHandle;
  UCHAR                      Response;
};
````

## Members


`BtAddress`

The Bluetooth address of the remote device to open a SCO channel to.

`Callback`

The 
     <a href="..\bthddi\nc-bthddi-pfnsco_indication_callback.md">SCO Callback Function</a> implemented by
     the profile driver, that the Bluetooth driver stack should call to notify the profile driver about any
     changes to the SCO connection.

`CallbackContext`

The context to pass to the callback function specified in the 
     <b>Callback</b> member. The profile driver defines this value.

`CallbackFlags`

A flag that specifies when the function assigned to the 
     <b>Callback</b> member should be sent to the client. Currently, there is only one valid flag:
     

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
SCO_CALLBACK_DISCONNECT

</td>
<td>
The profile driver should be notified when the remote device is disconnected.

</td>
</tr>
</table>

`ChannelFlags`

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

`ChannelHandle`

A handle to identify the SCO channel, if the open channel request completes successfully.

`ContentFormat`

The audio voice settings for the channel. Use the following definitions to encode this member:
     


<dl>
<dt>SCO_VS_AIR_CODING_DATA
     </dt>
<dt>SCO_VS_AIR_CODING_FORMAT_ALAW
     </dt>
<dt>SCO_VS_AIR_CODING_FORMAT_CVSD
     </dt>
<dt>SCO_VS_AIR_CODING_FORMAT_MASK
     </dt>
<dt>SCO_VS_AIR_CODING_FORMAT_MULAW
     </dt>
<dt>SCO_VS_IN_CODING_ALAW 
     </dt>
<dt>SCO_VS_IN_CODING_LINEAR
     </dt>
<dt>SCO_VS_IN_CODING_MASK
     </dt>
<dt>SCO_VS_IN_CODING_MULAW
     </dt>
<dt>SCO_VS_IN_DATA_FORMAT_1C
     </dt>
<dt>SCO_VS_IN_DATA_FORMAT_2C
     </dt>
<dt>SCO_VS_IN_DATA_FORMAT_MASK
     </dt>
<dt>SCO_VS_IN_DATA_FORMAT_SM
     </dt>
<dt>SCO_VS_IN_DATA_FORMAT_US
     </dt>
<dt>SCO_VS_IN_SAMPLE_SIZE_8BIT
     </dt>
<dt>SCO_VS_IN_SAMPLE_SIZE_16BIT
     </dt>
<dt>SCO_VS_IN_SAMPLE_SIZE_MASK
     </dt>
<dt>SCO_VS_PCM_BIT_POS_MASK
     </dt>
<dt>SCO_VS_SETTING_DEFAULT</dt>
</dl>

`Hdr`

A 
     <a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a> structure that contains information
     about the current BRB.

`MaxLatency`

A value that represents, in milliseconds, the upper limit of the sum of the synchronous interval
     and the size of the (e)SCO window. Possible values are listed in the following table.
     

<table>
<tr>
<td>
<b>
         Values</b>

</td>
<td>
<b>Description</b>

</td>
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
The range of possible 
        <b>MaxLatency</b> values for the channel.

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

`PacketType`

A flag or combination of flags that indicate the type of data packets that the SCO connection
     supports. These SCO packet types are defined by the Bluetooth SIG. See the Bluetooth specification for
     more information about these flags. Possible values include:
     



#### SCO_HV1



#### SCO_HV2



#### SCO_HV3



#### SCO_EV3



#### SCO_EV4



#### SCO_EV5

`ReceiveBandwidth`

The reception bandwidth, in bytes per second, to be assigned to the SCO channel.

`ReferenceObject`

A pointer to an object to pass to 
     <a href="..\wdm\nf-wdm-obreferenceobject.md">ObReferenceObject</a> and 
     <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a> for which to
     maintain a reference count of.

`Reserved`

Reserved for future use. Do not use.

`Response`

A flag that indicates whether the local server will accept or reject an incoming SCO connection.
     This member is used only when building and sending a <b>BRB_SCO_OPEN_CHANNEL_RESPONSE</b> request. Valid flag
     values are listed in the following table.
     

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
SCO_CONNECT_RSP_RESPONSE_SUCCESS

</td>
<td>
The local server accepts the SCO connection request.

</td>
</tr>
<tr>
<td>
SCO_CONNECT_RSP_RESPONSE_NO_RESOURCES

</td>
<td>
The local server rejects the SCO connection request due to a lack of resources.

</td>
</tr>
<tr>
<td>
SCO_CONNECT_RSP_RESPONSE_SECURITY_BLOCK

</td>
<td>
The local server rejects the SCO connection request because the request does not meet security
        requirements.

</td>
</tr>
<tr>
<td>
SCO_CONNECT_RSP_RESPONSE_BAD_BD_ADDR

</td>
<td>
The local server rejects the SCO connection request because it does not accept connections from
        the specified Bluetooth device address.

</td>
</tr>
</table>

`RetransmissionEffort`

A 
     <a href="..\bthddi\ne-bthddi-_sco_retransmission_effort.md">
     SCO_RETRANSMISSION_EFFORT</a> enumeration value that determines the retransmission policies for the
     channel.

`TransmitBandwidth`

The transmission bandwidth, in bytes per second, to be assigned to the SCO channel.

## Remarks
To open a SCO channel, profile drivers should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536626">BRB_SCO_OPEN_CHANNEL</a> request.

If the asynchronous connectionless link to the remote device does not exist prior to the request, the
    Bluetooth driver stack creates one before it creates the SCO channel.

To accept or reject an incoming SCO connection request initiated by a remote device, profile drivers
    should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://social.msdn.microsoft.com/Forums/en-US/0a9a4323-d046-4d27-9d22-4974dbab30a4/windows-bluetooth-sco-brbscoopenchannelresponse?forum=wdk">
    BRB_SCO_OPEN_CHANNEL_RESPONSE</a> request.

A profile driver should build and send a <b>BRB_SCO_OPEN_CHANNEL_RESPONSE</b> request when the Bluetooth
    driver stack calls the profile driver's 
    <a href="..\bthddi\nc-bthddi-pfnsco_indication_callback.md">SCO Callback Function</a> and passes 
    <b>ScoIndicationRemoteConnect</b> in the callback function's 
    <i>Indication</i> parameter.

The profile driver specifies whether the connection should be accepted by storing an appropriate value
    in the 
    <b>Response</b> member of this structure. In this context, the local system is the server.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later. Versions:\_Supported in Windows Vista, and later. |
| **Header** | bthddi.h (include Bthddi.h) |

## See Also

<a href="..\bthddi\ne-bthddi-_sco_retransmission_effort.md">SCO_RETRANSMISSION_EFFORT</a>



<a href="https://social.msdn.microsoft.com/Forums/en-US/0a9a4323-d046-4d27-9d22-4974dbab30a4/windows-bluetooth-sco-brbscoopenchannelresponse?forum=wdk">BRB_SCO_OPEN_CHANNEL_RESPONSE</a>



<a href="..\wdm\nf-wdm-obreferenceobject.md">ObReferenceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536626">BRB_SCO_OPEN_CHANNEL</a>



<a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a>



<a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>



<a href="..\bthddi\nc-bthddi-pfnsco_indication_callback.md">SCO Callback Function</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20_BRB_SCO_OPEN_CHANNEL structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>