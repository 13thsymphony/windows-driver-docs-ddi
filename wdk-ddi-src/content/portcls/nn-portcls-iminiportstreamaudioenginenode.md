---
UID: NN:portcls.IMiniportStreamAudioEngineNode
title: IMiniportStreamAudioEngineNode
author: windows-driver-content
description: This interface allows a miniport driver to use KS properties that access the audio engine via a pin instance handle.
old-location: audio\iminiportstreamaudioenginenode.htm
old-project: audio
ms.assetid: B3F7D3AC-C756-47D2-9E7C-7930621753C3
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcUnregisterIoTimeout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IMiniportStreamAudioEngineNode
req.alt-loc: Portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PPC_EXIT_LATENCY, PC_EXIT_LATENCY
---

# IMiniportStreamAudioEngineNode interface



## -description
This interface allows a miniport driver to use KS properties that access the audio engine via a pin instance handle.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IMiniportStreamAudioEngineNode</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IMiniportStreamAudioEngineNode</b> also has these types of members:

The <b>IMiniportStreamAudioEngineNode</b> interface has these methods.

Gets the state of the local effects (LFX) node that is in the path of the audio stream.

Gets the allowed stepping value for the audio stream attribute.

Gets a count of the number of channels available for the stream.

Gets the state of the Mute node in the path of the audio stream.

Gets the value of the PeakMeter node in the path of the audio stream.

Gets the current volume level that is applied to the audio stream.

	Gets the number of bytes that the DMA has fetched from the audio buffer since the beginning of the stream.

Gets the current cursor position in the audio data stream that is being rendered to the endpoint.

Sets the state of the local effects (LFX) node that is in the path of the audio stream.

Sets the state of the Mute node in the path of the audio stream.

Sets the volume level to be applied to the audio stream.

Sets the current cursor position in the audio data stream that is being captured from the endpoint.

Sets the loopback protection status of the audio engine node.

 


## -members
The <b>IMiniportStreamAudioEngineNode</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265091">GetLfxState</a>
</td>
<td align="left" width="63%">
Gets the state of the local effects (LFX) node that is in the path of the audio stream.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265092">GetStreamAttributeSteppings</a>
</td>
<td align="left" width="63%">
Gets the allowed stepping value for the audio stream attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265093">GetStreamChannelCount</a>
</td>
<td align="left" width="63%">
Gets a count of the number of channels available for the stream.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265094">GetStreamChannelMute</a>
</td>
<td align="left" width="63%">
Gets the state of the Mute node in the path of the audio stream.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265095">GetStreamChannelPeakMeter</a>
</td>
<td align="left" width="63%">
Gets the value of the PeakMeter node in the path of the audio stream.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265096">GetStreamChannelVolume</a>
</td>
<td align="left" width="63%">
Gets the current volume level that is applied to the audio stream.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265097">GetStreamLinearBufferPosition</a>
</td>
<td align="left" width="63%">
	Gets the number of bytes that the DMA has fetched from the audio buffer since the beginning of the stream.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265098">GetStreamPresentationPosition</a>
</td>
<td align="left" width="63%">
Gets the current cursor position in the audio data stream that is being rendered to the endpoint.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265099">SetLfxState</a>
</td>
<td align="left" width="63%">
Sets the state of the local effects (LFX) node that is in the path of the audio stream.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265100">SetStreamChannelMute</a>
</td>
<td align="left" width="63%">
Sets the state of the Mute node in the path of the audio stream.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265101">SetStreamChannelVolume</a>
</td>
<td align="left" width="63%">
Sets the volume level to be applied to the audio stream.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265102">SetStreamCurrentWritePosition</a>
</td>
<td align="left" width="63%">
Sets the current cursor position in the audio data stream that is being captured from the endpoint.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265103">SetStreamLoopbackProtection</a>
</td>
<td align="left" width="63%">
Sets the loopback protection status of the audio engine node.

</td>
</tr>
</table>Gets the state of the local effects (LFX) node that is in the path of the audio stream.

Gets the allowed stepping value for the audio stream attribute.

Gets a count of the number of channels available for the stream.

Gets the state of the Mute node in the path of the audio stream.

Gets the value of the PeakMeter node in the path of the audio stream.

Gets the current volume level that is applied to the audio stream.

	Gets the number of bytes that the DMA has fetched from the audio buffer since the beginning of the stream.

Gets the current cursor position in the audio data stream that is being rendered to the endpoint.

Sets the state of the local effects (LFX) node that is in the path of the audio stream.

Sets the state of the Mute node in the path of the audio stream.

Sets the volume level to be applied to the audio stream.

Sets the current cursor position in the audio data stream that is being captured from the endpoint.

Sets the loopback protection status of the audio engine node.

 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h</dt>
</dl>
</td>
</tr>
</table>