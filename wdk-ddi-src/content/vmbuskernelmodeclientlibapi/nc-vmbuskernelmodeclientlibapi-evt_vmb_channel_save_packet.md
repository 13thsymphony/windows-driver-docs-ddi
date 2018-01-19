---
UID : NC:vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_SAVE_PACKET
title : EVT_VMB_CHANNEL_SAVE_PACKET
author : windows-driver-content
description : The EvtVmbChannelSavePacket callback function is invoked when the virtualization service provider (VSP) endpoint must save the state associated with a packet.
old-location : netvista\evt_vmb_channel_save_packet.htm
old-project : netvista
ms.assetid : 92CC3C36-D10C-4C6B-8BB4-476E72AD684C
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
req.alt-api : PFN_VMB_CHANNEL_SAVE_PACKET
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
req.irql : PASSIVE_LEVEL
req.typenames : "*PVIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES"
req.product : Windows 10 or later.
---


# EVT_VMB_CHANNEL_SAVE_PACKET function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtVmbChannelSavePacket</i> callback function is invoked when the virtualization service provider (VSP) endpoint must save the state associated with a packet.

## Syntax

```
EVT_VMB_CHANNEL_SAVE_PACKET EvtVmbChannelSavePacket;

NTSTATUS EvtVmbChannelSavePacket(
  VMBCHANNEL Channel,
  VMBPACKET Packet,
  PVOID SaveBuf,
  UINT32 SaveBufSize,
  PUINT32 BytesNeeded
)
{...}
```

## Parameters

`Channel`

The channel on which the packet arrives.

`Packet`

The packet for which VSP saves state.

`SaveBuf`

The buffer into which to save the state.

`SaveBufSize`

Size of the <i>SaveBuf</i> parameter, in bytes.

`BytesNeeded`

Size necessary to save the state of the transaction, in bytes.


## Return Value

<i>EvtVmbChannelSavePacket</i> returns a status code.

## Remarks

The <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbserverchannelinitsetsaverestorepacketcallbacks.md">VmbServerChannelInitSetSaveRestorePacketCallbacks</a> function sets a callback function for saving packets for each channel.

The VSP saves the state associated with the transaction that is unique to the VSP.  The Kernel Mode Client Library (KMCL)
saves its own state.

This function is invoked for each packet object that is currently in use.  The first invocation passes a zero (0) value for the <i>SaveBufSize</i> parameter.  This call fails if there is any state that needs to be saved, which fills the <i>BytesNeeded</i> with the actual size requirement.  If this first invocation
returns a failure code, the KMCL calls a second time with a buffer of at least
the length stipulated in the first call.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbserverchannelinitsetsaverestorepacketcallbacks.md">VmbServerChannelInitSetSaveRestorePacketCallbacks</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20EVT_VMB_CHANNEL_SAVE_PACKET callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>