---
UID: NC:vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_CLOSED
title: EVT_VMB_CHANNEL_CLOSED
author: windows-driver-content
description: The EvtVmbChannelClosed callback function is invoked when the client endpoint in the guest virtual machine closes a channel by using the VmbChannelDisable function, or the opposite endpoint rescinds or closes the channel.
old-location: netvista\evt_vmb_channel_closed.htm
old-project: netvista
ms.assetid: 457FADB8-4126-43A8-AA38-E3D722728459
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: EVT_VMB_CHANNEL_CLOSED, EvtVmbChannelClosed, EvtVmbChannelClosed callback function [Network Drivers Starting with Windows Vista], PFN_VMB_CHANNEL_CLOSED, PFN_VMB_CHANNEL_CLOSED callback function pointer [Network Drivers Starting with Windows Vista], netvista.evt_vmb_channel_closed, vmbuskernelmodeclientlibapi/EvtVmbChannelClosed
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	VmbusKernelModeClientLibApi.h
api_name:
-	PFN_VMB_CHANNEL_CLOSED
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---


# EVT_VMB_CHANNEL_CLOSED callback function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtVmbChannelClosed</i> callback function is invoked when the client endpoint in the guest virtual machine closes a
channel by using the <a href="https://msdn.microsoft.com/688A1DF3-F801-47C3-8403-9FA5D96BD428">VmbChannelDisable</a> function, or the opposite endpoint rescinds or closes the 
channel.

## Syntax

```
EVT_VMB_CHANNEL_CLOSED EvtVmbChannelClosed;

void EvtVmbChannelClosed(
  VMBCHANNEL Channel
)
{...}
```

## Parameters

`Channel`

The channel that the guest virtual machine closes.


## Return Value

This callback function does not return a value.

## Remarks

After a channel is created, a client driver can specify callback functions for state changes, including  <i>EvtVmbChannelClosed</i>, by using the <a href="https://msdn.microsoft.com/2255C8A2-85FB-4B96-8AE9-66FAFD73EE73">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a> function.

After this callback function finishes on the host, the channel 
is either closed or disabled, depending on whether the guest closed 
the channel or the Kernel Mode Client Library (KMCL) client called <a href="https://msdn.microsoft.com/688A1DF3-F801-47C3-8403-9FA5D96BD428">VmbChannelDisable</a>, 
respectively.  

On the guest, the channel always becomes disabled. It 
must be restarted by using the <a href="https://msdn.microsoft.com/A0256B3F-C35C-45AB-A825-0A82189F08DC">VmbChannelEnable</a> function.  

After this  is function invoked, packets can be queued, but they cannot be sent.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/2255C8A2-85FB-4B96-8AE9-66FAFD73EE73">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a>



<a href="https://msdn.microsoft.com/688A1DF3-F801-47C3-8403-9FA5D96BD428">VmbChannelDisable</a>



<a href="https://msdn.microsoft.com/A0256B3F-C35C-45AB-A825-0A82189F08DC">VmbChannelEnable</a>