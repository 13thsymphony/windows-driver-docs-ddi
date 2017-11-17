---
UID: NC.vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_SUSPEND
title: EVT_VMB_CHANNEL_SUSPEND
author: windows-driver-content
description: The EvtVmbChannelSuspend callback function is invoked at the server endpoint when the channel is being closed or deleted by the client endpoint, which moves the server into the Stopped state.
old-location: netvista\evt_vmb_channel_suspend.htm
ms.assetid: 31FED6BE-2E89-4D36-A833-9144AD61B885
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: netvista
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PFN_VMB_CHANNEL_SUSPEND
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
ms.keywords: VideoPortGetAgpServices
req.iface: 
req.product: Windows 10 or later.
---

# EVT_VMB_CHANNEL_SUSPEND callback



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]</p>
<p>The <i>EvtVmbChannelSuspend</i> callback function is invoked at the server endpoint when the channel is being
closed or deleted by the client endpoint, which moves the server into the Stopped
state.  </p>


## -prototype

````
EVT_VMB_CHANNEL_SUSPEND EvtVmbChannelSuspend;

VOID EvtVmbChannelSuspend(
  _In_ VMBCHANNEL Channel
)
{ ... }

typedef EVT_VMB_CHANNEL_SUSPEND PFN_VMB_CHANNEL_SUSPEND;
````


## -parameters
<dl>

### -param <i>Channel</i> [in]

<dd>
<p>The channel which is suspended.</p>
</dd>
</dl>

## -returns
<p>This callback function does not return a value.</p>

## -remarks
<p>After a channel is created, a client driver can specify callback functions for state changes, including  <i>EvtVmbChannelSuspend</i>, by using the <a href="https://msdn.microsoft.com/2255C8A2-85FB-4B96-8AE9-66FAFD73EE73">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a> function.</p>

<p>If a running channel is suspended by using the <a href="https://msdn.microsoft.com/434CA5F7-24D4-40E7-AE77-C0732D3FBBFF">VmbChannelPause</a> function or closed by using the <a href="https://msdn.microsoft.com/688A1DF3-F801-47C3-8403-9FA5D96BD428">VmbChannelDisable</a> function or by the opposite endpoint, Kernel Mode Client Library (KMCL) calls <i>EvtVmbChannelSuspend</i>.  This callback guarantees that no more 
<a href="https://msdn.microsoft.com/46020122-0B0E-4C05-8B13-68100B227E93">EvtVmbChannelProcessPacket</a> callbacks are running or will be queued.</p>

<p><i>EvtVmbChannelSuspend</i> is also a 
notification that the KMCL client must eventually complete all outstanding 
packets indicated by using  <a href="https://msdn.microsoft.com/46020122-0B0E-4C05-8B13-68100B227E93">EvtVmbChannelProcessPacket</a> These packets do 
not have to be completed synchronously.  KMCL blocks until they have 
been completed.  </p>

<p>The KMCL client must also stop sending packets by using the <a href="https://msdn.microsoft.com/EBB981CB-0107-497A-B6E6-9271E22A8D5F">VmbPacketSend</a>, <a href="https://msdn.microsoft.com/C1B3FA0C-65B8-4CE1-B8F5-650DF54C9E1E">VmbPacketSendWithExternalMdl</a>, or <a href="https://msdn.microsoft.com/50AACCAB-EFEA-42B7-8A34-FE110C7CDEED">VmbPacketSendWithExternalPfns</a> functions.  

</p>

<p>A call to <a href="https://msdn.microsoft.com/434CA5F7-24D4-40E7-AE77-C0732D3FBBFF">VmbChannelPause</a> on an active channel blocks until 
<i>EvtVmbChannelSuspend</i> is called and no more outstanding incoming packets exist.  
A call to <a href="https://msdn.microsoft.com/688A1DF3-F801-47C3-8403-9FA5D96BD428">VmbChannelDisable</a> block until the channel is paused and closed.</p>

<p>This function does guarantee completion of outstanding transactions.  The client may be buggy, malicious,
or the guest virtual machine may have crashed.  The server must retire any outstanding transactions, probably by cancelling them. </p>

<p>After a channel is created, a client driver can specify callback functions for state changes, including  <i>EvtVmbChannelSuspend</i>, by using the <a href="https://msdn.microsoft.com/2255C8A2-85FB-4B96-8AE9-66FAFD73EE73">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a> function.</p>

<p>If a running channel is suspended by using the <a href="https://msdn.microsoft.com/434CA5F7-24D4-40E7-AE77-C0732D3FBBFF">VmbChannelPause</a> function or closed by using the <a href="https://msdn.microsoft.com/688A1DF3-F801-47C3-8403-9FA5D96BD428">VmbChannelDisable</a> function or by the opposite endpoint, Kernel Mode Client Library (KMCL) calls <i>EvtVmbChannelSuspend</i>.  This callback guarantees that no more 
<a href="https://msdn.microsoft.com/46020122-0B0E-4C05-8B13-68100B227E93">EvtVmbChannelProcessPacket</a> callbacks are running or will be queued.</p>

<p><i>EvtVmbChannelSuspend</i> is also a 
notification that the KMCL client must eventually complete all outstanding 
packets indicated by using  <a href="https://msdn.microsoft.com/46020122-0B0E-4C05-8B13-68100B227E93">EvtVmbChannelProcessPacket</a> These packets do 
not have to be completed synchronously.  KMCL blocks until they have 
been completed.  </p>

<p>The KMCL client must also stop sending packets by using the <a href="https://msdn.microsoft.com/EBB981CB-0107-497A-B6E6-9271E22A8D5F">VmbPacketSend</a>, <a href="https://msdn.microsoft.com/C1B3FA0C-65B8-4CE1-B8F5-650DF54C9E1E">VmbPacketSendWithExternalMdl</a>, or <a href="https://msdn.microsoft.com/50AACCAB-EFEA-42B7-8A34-FE110C7CDEED">VmbPacketSendWithExternalPfns</a> functions.  

</p>

<p>A call to <a href="https://msdn.microsoft.com/434CA5F7-24D4-40E7-AE77-C0732D3FBBFF">VmbChannelPause</a> on an active channel blocks until 
<i>EvtVmbChannelSuspend</i> is called and no more outstanding incoming packets exist.  
A call to <a href="https://msdn.microsoft.com/688A1DF3-F801-47C3-8403-9FA5D96BD428">VmbChannelDisable</a> block until the channel is paused and closed.</p>

<p>This function does guarantee completion of outstanding transactions.  The client may be buggy, malicious,
or the guest virtual machine may have crashed.  The server must retire any outstanding transactions, probably by cancelling them. </p>

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
<a href="https://msdn.microsoft.com/46020122-0B0E-4C05-8B13-68100B227E93">EvtVmbChannelProcessPacket</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/2255C8A2-85FB-4B96-8AE9-66FAFD73EE73">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/688A1DF3-F801-47C3-8403-9FA5D96BD428">VmbChannelDisable</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/434CA5F7-24D4-40E7-AE77-C0732D3FBBFF">VmbChannelPause</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/EBB981CB-0107-497A-B6E6-9271E22A8D5F">VmbPacketSend</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/C1B3FA0C-65B8-4CE1-B8F5-650DF54C9E1E">VmbPacketSendWithExternalMdl</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/50AACCAB-EFEA-42B7-8A34-FE110C7CDEED">VmbPacketSendWithExternalPfns</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20EVT_VMB_CHANNEL_SUSPEND callback function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
