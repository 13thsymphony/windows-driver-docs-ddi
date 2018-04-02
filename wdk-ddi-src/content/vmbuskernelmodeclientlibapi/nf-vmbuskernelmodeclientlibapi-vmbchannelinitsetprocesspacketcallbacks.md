---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelInitSetProcessPacketCallbacks
title: VmbChannelInitSetProcessPacketCallbacks function
author: windows-driver-content
description: The VmbChannelInitSetProcessPacketCallbacks function sets callback functions for packet processing.
old-location: netvista\vmbchannelinitsetprocesspacketcallbacks.htm
old-project: netvista
ms.assetid: 437DC9C5-CE73-45E8-AC4A-CFF9249809AD
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: VmbChannelInitSetProcessPacketCallbacks, VmbChannelInitSetProcessPacketCallbacks function [Network Drivers Starting with Windows Vista], netvista.vmbchannelinitsetprocesspacketcallbacks, vmbuskernelmodeclientlibapi/VmbChannelInitSetProcessPacketCallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Vmbkmcl.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	vmbkmcl.lib
-	vmbkmcl.dll
api_name:
-	VmbChannelInitSetProcessPacketCallbacks
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---


# VmbChannelInitSetProcessPacketCallbacks function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelInitSetProcessPacketCallbacks</b>  function sets callback functions for packet processing.

## Syntax

```
NTSTATUS VmbChannelInitSetProcessPacketCallbacks(
  VMBCHANNEL                          Channel,
  PFN_VMB_CHANNEL_PROCESS_PACKET      ProcessPacketCallback,
  PFN_VMB_CHANNEL_PROCESSING_COMPLETE ProcessingCompleteCallback
);
```

## Parameters

`Channel`

A handle for the channel.

`ProcessPacketCallback`

A callback function to call when a packet is     ready for processing.

`ProcessingCompleteCallback`

A callback function to call     when processing of a batch of packets has been completed.


## Return Value

returns one of the following status values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The function finished successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b> STATUS_INVALID_PARAMETER_1</b></dt>
</dl>
</td>
<td width="60%">
The <i>Channel</i> value was invalid or in an invalid state, such as Disabled.

</td>
</tr>
</table>

## Remarks

This function is only meaningful if Kernel Mode Client Library (KMCL) queue
management is not suppressed.  

<b>ProcessPacketCallback</b> is invoked for every packet that
is received.  <a href="https://msdn.microsoft.com/E30A169E-0EC6-4128-B268-5FC1CD37A877">EvtVmbChannelProcessingComplete</a> will be invoked every time the ring buffer that contains incoming packets transitions from non-empty to empty. This happens
after the last invocation of <b>ProcessPacketCallback</b> in a single batch.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **Library** | Vmbkmcl.lib |

## See Also

<a href="https://msdn.microsoft.com/E30A169E-0EC6-4128-B268-5FC1CD37A877">EvtVmbChannelProcessingComplete</a>



<a href="https://msdn.microsoft.com/437DC9C5-CE73-45E8-AC4A-CFF9249809AD">ProcessPacketCallback</a>