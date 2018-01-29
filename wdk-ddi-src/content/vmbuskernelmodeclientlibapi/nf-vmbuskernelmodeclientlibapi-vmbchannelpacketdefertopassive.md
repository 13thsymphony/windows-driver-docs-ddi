---
UID : NF:vmbuskernelmodeclientlibapi.VmbChannelPacketDeferToPassive
title : VmbChannelPacketDeferToPassive function
author : windows-driver-content
description : The VmbChannelPacketDeferToPassive function is called by the client driver to defer a packet passed to it by the EvtVmbChannelProcessPacket callback function.
old-location : netvista\vmbchannelpacketdefertopassive.htm
old-project : netvista
ms.assetid : 796F849F-7281-4AE9-BE0D-350D24A39C61
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : VmbChannelPacketDeferToPassive function [Network Drivers Starting with Windows Vista], VmbChannelPacketDeferToPassive, vmbuskernelmodeclientlibapi/VmbChannelPacketDeferToPassive, netvista.vmbchannelpacketdefertopassive
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : vmbuskernelmodeclientlibapi.h
req.include-header : VmbusKernelModeClientLibApi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : Windows Server 2012 R2
req.kmdf-ver : 1.13
req.umdf-ver : 2.0
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Vmbkmcl.lib
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product : Windows 10 or later.
---


# VmbChannelPacketDeferToPassive function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelPacketDeferToPassive</b> function is called by the client driver to defer a packet
passed to it by the <a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_process_packet.md">EvtVmbChannelProcessPacket</a> callback function.

## Syntax

````
VOID VmbChannelPacketDeferToPassive(
  _In_ VMBPACKETCOMPLETION PacketCompletionContext
);
````

## Parameters

`PacketCompletionContext`

A  handle that identifies the incoming packet and is used to refer to the packet
once processing is finished.


## Return Value

This function does not return a value.

## Remarks

A deferred packet goes back onto the parsing queue. It is guaranteed to be
parsed again at PASSIVE_LEVEL.


This routine is designed to only be called in-line from <a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_process_packet.md">EvtVmbChannelProcessPacket</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_process_packet.md">EvtVmbChannelProcessPacket</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbChannelPacketDeferToPassive function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>