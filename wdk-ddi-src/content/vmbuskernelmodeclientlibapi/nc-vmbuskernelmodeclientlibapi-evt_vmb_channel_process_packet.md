---
UID: NC.vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_PROCESS_PACKET
title: EVT_VMB_CHANNEL_PROCESS_PACKET
author: windows-driver-content
description: The EvtVmbChannelProcessPacket callback function is invoked when a packet arrives in the incoming ring buffer.
old-location: netvista\evt_vmb_channel_process_packet.htm
old-project: netvista
ms.assetid: 46020122-0B0E-4C05-8B13-68100B227E93
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: VideoPortGetAgpServices
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PFN_VMB_CHANNEL_PROCESS_PACKET
req.alt-loc: VmbusKernelModeClientLibApi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# EVT_VMB_CHANNEL_PROCESS_PACKET callback



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtVmbChannelProcessPacket</i> callback function is invoked when a packet arrives in the incoming ring buffer.




## -prototype

````
EVT_VMB_CHANNEL_PROCESS_PACKET EvtVmbChannelProcessPacket;

VOID EvtVmbChannelProcessPacket(
  _In_ VMBCHANNEL                       Channel,
  _In_ VMBPACKETCOMPLETION              Packet,
  _In_ reads_bytes_(BufferLength) PVOID Buffer,
  _In_ UINT32                           BufferLength,
  _In_ UINT32                           Flags
)
{ ... }

typedef EVT_VMB_CHANNEL_PROCESS_PACKET PFN_VMB_CHANNEL_PROCESS_PACKET;
````


## -parameters

### -param Channel [in]

The channel on which the packet arrives.


### -param Packet [in]

The completion context, which identifies this packet to Kernel Mode Client Library (KMCL) when the transaction can be retired.



### -param Buffer [in]

The packet which was sent by the opposite endpoint.  This value does not contain the VMBus and KMCL headers.



### -param BufferLength [in]

The length of the <i>Buffer</i> parameter, in bytes.


### -param Flags [in]

Flags. Possible values include the following: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param VMBUS_CHANNEL_PROCESS_PACKET_FLAGS
### -param 0x1

</td>
<td width="60%">
The packet references
external data. This data can be retrieved by using
the <a href="netvista.vmbchannelpacketgetexternaldata">VmbChannelPacketGetExternalData</a> function.

</td>
</tr>
</table>
 


## -returns
This callback function does not return a value.


## -remarks
The client driver registers its implementation of this callback function by using the <a href="netvista.vmbchannelinitsetprocesspacketcallbacks">VmbChannelInitSetProcessPacketCallbacks</a> function. 

Every time you invoke this function, you must eventually call
the <a href="netvista.vmbchannelpacketcomplete">VmbChannelPacketComplete</a> function.

This callback function can be invoked at DISPATCH_LEVEL or lower, unless the channel
has been configured to defer packet processing to a worker thread.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>VmbusKernelModeClientLibApi.h (include VmbusKernelModeClientLibApi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.vmbchannelinitsetprocesspacketcallbacks">VmbChannelInitSetProcessPacketCallbacks</a>
</dt>
<dt>
<a href="netvista.vmbchannelpacketcomplete">VmbChannelPacketComplete</a>
</dt>
<dt>
<a href="netvista.vmbchannelpacketgetexternaldata">VmbChannelPacketGetExternalData</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20EVT_VMB_CHANNEL_PROCESS_PACKET callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

