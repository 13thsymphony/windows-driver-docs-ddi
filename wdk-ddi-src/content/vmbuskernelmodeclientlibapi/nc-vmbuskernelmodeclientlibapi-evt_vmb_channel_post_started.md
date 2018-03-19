---
UID: NC:vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_POST_STARTED
title: EVT_VMB_CHANNEL_POST_STARTED
author: windows-driver-content
description: The EvtVmbChannelPostStarted callback function is invoked at either endpoint after packets can be received from the opposite endpoint.
old-location: netvista\evt_vmb_channel_post_started.htm
old-project: netvista
ms.assetid: 0F48459F-BA02-4A0E-9228-BC064A6AD150
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EVT_VMB_CHANNEL_POST_STARTED, EvtVmbChannelPostStarted, EvtVmbChannelPostStarted callback function [Network Drivers Starting with Windows Vista], PFN_VMB_CHANNEL_POST_STARTED, PFN_VMB_CHANNEL_POST_STARTED callback function pointer [Network Drivers Starting with Windows Vista], netvista.evt_vmb_channel_post_started, vmbuskernelmodeclientlibapi/EvtVmbChannelPostStarted
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
-	PFN_VMB_CHANNEL_POST_STARTED
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---


# EVT_VMB_CHANNEL_POST_STARTED callback function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtVmbChannelPostStarted</i> callback function is invoked at either endpoint after packets can be received from
the opposite endpoint.

## Syntax

```
EVT_VMB_CHANNEL_POST_STARTED EvtVmbChannelPostStarted;

void EvtVmbChannelPostStarted(
  VMBCHANNEL Channel
)
{...}
```

## Parameters

`Channel`

The channel for these endpoints.


## Return Value

This callback function does not return a value.

## Remarks

After a channel is created, a client driver can specify callback functions for state changes, including  <i>EvtVmbChannelPostStarted</i>, by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmb_channel_state_change_callbacks_init.md">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a> function.

After a channel has been  
configured, the Kernel Mode Client Library (KMCL) client calls the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelenable.md">VmbChannelEnable</a> function to open the channel.  When a channel is opened, KMCL invokes the <a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_opened.md">EvtVmbChannelOpened</a> callback function. After the channel endpoints can receive packets but before packets are processed, KMCL invokes the <i>EvtVmbChannelPostStarted</i> callback.

You can wait for sent packets to complete in this function, such as by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsendsynchronousrequest.md">VmbChannelSendSynchronousRequest</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_post_started.md">EvtVmbChannelPostStarted</a>



<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelenable.md">VmbChannelEnable</a>



<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsendsynchronousrequest.md">VmbChannelSendSynchronousRequest</a>



<a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_opened.md">EvtVmbChannelOpened</a>



<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmb_channel_state_change_callbacks_init.md">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a>