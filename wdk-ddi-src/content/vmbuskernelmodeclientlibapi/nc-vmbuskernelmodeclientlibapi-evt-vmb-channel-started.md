---
UID: NC.vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_STARTED
title: EVT_VMB_CHANNEL_STARTED
author: windows-driver-content
description: The EvtVmbChannelStarted callback function is invoked at either endpoint when a channel is fully configured but before any packets have been delivered. This occurs when the opposite endpoint opened the channel or reopened it after closing it.
old-location: netvista\evt_vmb_channel_started.htm
old-project: netvista
ms.assetid: C4F35016-3F93-4258-A42F-D692AF690020
ms.author: windowsdriverdev
ms.date: 11/22/2017
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
req.alt-api: PFN_VMB_CHANNEL_STARTED
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
req.irql: PASSIVE_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# EVT_VMB_CHANNEL_STARTED callback



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]</p>
<p>The <i>EvtVmbChannelStarted</i> callback function is invoked at either endpoint when a channel is
fully configured but before any packets have been delivered.  This occurs when the opposite endpoint opened the channel or reopened it after closing it.  </p>


## -prototype

````
EVT_VMB_CHANNEL_STARTED EvtVmbChannelStarted;

VOID EvtVmbChannelStarted(
  _In_ VMBCHANNEL Channel
)
{ ... }

typedef EVT_VMB_CHANNEL_STARTED PFN_VMB_CHANNEL_STARTED;
````


## -parameters
<dl>

### -param <i>Channel</i> [in]

<dd>
<p>The channel which is started.</p>
</dd>
</dl>

## -returns
<p>This callback function does not return a value.</p>

## -remarks
<p>After a channel is created, a client driver can specify callback functions for state changes, including  <i>EvtVmbChannelStarted</i>, by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmb-channel-state-change-callbacks-init.md">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a> function.</p>

<p>If a paused channel is opened or an opened channel is started, Kernel Mode Client Library (KMCL) calls <i>EvtVmbChannelStarted</i> after it calls the <a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt-vmb-channel-opened.md">EvtVmbChannelOpened</a> callback.  <i>EvtVmbChannelStarted</i> can call the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsend.md">VmbPacketSend</a>, <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsendwithexternalmdl.md">VmbPacketSendWithExternalMdl</a>, and <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsendwithexternalpfns.md">VmbPacketSendWithExternalPfns</a> functions 
to queue up outgoing packets. Because the incoming queue is not running at this point, this callback must not block on incoming packets or 
completions.  </p>

<p>Most drivers using KMCL do not implement
this callback. An alternative is the <a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt-vmb-channel-post-started.md">EvtVmbChannelPostStarted</a> callback function.</p>

<p>Waiting for a sent packet to complete, such as by the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsendsynchronousrequest.md">VmbChannelSendSynchronousRequest</a> function, never returns because packets are not flowing when this callback is invoked.</p>

<p>After a channel is created, a client driver can specify callback functions for state changes, including  <i>EvtVmbChannelStarted</i>, by using the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmb-channel-state-change-callbacks-init.md">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a> function.</p>

<p>If a paused channel is opened or an opened channel is started, Kernel Mode Client Library (KMCL) calls <i>EvtVmbChannelStarted</i> after it calls the <a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt-vmb-channel-opened.md">EvtVmbChannelOpened</a> callback.  <i>EvtVmbChannelStarted</i> can call the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsend.md">VmbPacketSend</a>, <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsendwithexternalmdl.md">VmbPacketSendWithExternalMdl</a>, and <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsendwithexternalpfns.md">VmbPacketSendWithExternalPfns</a> functions 
to queue up outgoing packets. Because the incoming queue is not running at this point, this callback must not block on incoming packets or 
completions.  </p>

<p>Most drivers using KMCL do not implement
this callback. An alternative is the <a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt-vmb-channel-post-started.md">EvtVmbChannelPostStarted</a> callback function.</p>

<p>Waiting for a sent packet to complete, such as by the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsendsynchronousrequest.md">VmbChannelSendSynchronousRequest</a> function, never returns because packets are not flowing when this callback is invoked.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>VmbusKernelModeClientLibApi.h (include VmbusKernelModeClientLibApi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt-vmb-channel-opened.md">EvtVmbChannelOpened</a>
</dt>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nc-vmbuskernelmodeclientlibapi-evt-vmb-channel-post-started.md">EvtVmbChannelPostStarted</a>
</dt>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmb-channel-state-change-callbacks-init.md">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a>
</dt>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsendsynchronousrequest.md">VmbChannelSendSynchronousRequest</a>
</dt>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsend.md">VmbPacketSend</a>
</dt>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsendwithexternalmdl.md">VmbPacketSendWithExternalMdl</a>
</dt>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsendwithexternalpfns.md">VmbPacketSendWithExternalPfns</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20EVT_VMB_CHANNEL_STARTED callback function%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
