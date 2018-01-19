---
UID : NC:vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_PROCESS_PACKET
title : EVT_VMB_CHANNEL_PROCESS_PACKET
author : windows-driver-content
description : The EvtVmbChannelProcessPacket callback function is invoked when a packet arrives in the incoming ring buffer.
old-location : netvista\evt_vmb_channel_process_packet.htm
old-project : netvista
ms.assetid : 46020122-0B0E-4C05-8B13-68100B227E93
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : vmbuskernelmodeclientlibapi.h
req.include-header : VmbusKernelModeClientLibApi.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : PFN_VMB_CHANNEL_PROCESS_PACKET
req.alt-loc : VmbusKernelModeClientLibApi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <=DISPATCH_LEVEL
req.typenames : "*PVIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES"
req.product : Windows 10 or later.
---


# EVT_VMB_CHANNEL_PROCESS_PACKET function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtVmbChannelProcessPacket</i> callback function is invoked when a packet arrives in the incoming ring buffer.

## Syntax

```
EVT_VMB_CHANNEL_PROCESS_PACKET EvtVmbChannelProcessPacket;

void EvtVmbChannelProcessPacket(
  VMBCHANNEL Channel,
  VMBPACKETCOMPLETION Packet,
  PVOID Buffer,
  UINT32 BufferLength,
  UINT32 Flags
)
{...}
```

## Parameters

`Channel`

The channel on which the packet arrives.

`Packet`

The completion context, which identifies this packet to Kernel Mode Client Library (KMCL) when the transaction can be retired.

`Buffer`

The packet which was sent by the opposite endpoint.  This value does not contain the VMBus and KMCL headers.

`BufferLength`

The length of the <i>Buffer</i> parameter, in bytes.

`Flags`

Flags. Possible values include the following: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>


## Return Value

This callback function does not return a value.

## Remarks

The client driver registers its implementation of this callback function by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelinitsetprocesspacketcallbacks.md">VmbChannelInitSetProcessPacketCallbacks</a> function. 

Every time you invoke this function, you must eventually call
the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelpacketcomplete.md">VmbChannelPacketComplete</a> function.

This callback function can be invoked at DISPATCH_LEVEL or lower, unless the channel
has been configured to defer packet processing to a worker thread.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelinitsetprocesspacketcallbacks.md">VmbChannelInitSetProcessPacketCallbacks</a>
</dt>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelpacketcomplete.md">VmbChannelPacketComplete</a>
</dt>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelpacketgetexternaldata.md">VmbChannelPacketGetExternalData</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20EVT_VMB_CHANNEL_PROCESS_PACKET callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>