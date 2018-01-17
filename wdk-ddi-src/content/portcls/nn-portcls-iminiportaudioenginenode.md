---
UID: NN:portcls.IMiniportAudioEngineNode
title: IMiniportAudioEngineNode
author: windows-driver-content
description: This interface allows a miniport driver to use KS properties that access the audio engine via a KS filter handle.
old-location: audio\iminiportaudioenginenode.htm
old-project: audio
ms.assetid: 58170D54-869A-49CC-865A-AB64BFB41A4B
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
req.alt-api: IMiniportAudioEngineNode
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

# IMiniportAudioEngineNode interface



## -description
This interface allows a miniport driver to use KS properties that access the audio engine via a KS filter handle.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IMiniportAudioEngineNode</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IMiniportAudioEngineNode</b> also has these types of members:

The <b>IMiniportAudioEngineNode</b> interface has these methods.

Gets the descriptor for the audio engine node.

Gets the minimum and maximum buffer size that the hardware audio engine can support.

Gets the allowed stepping value for the audio device attribute.

Gets a count of the number of channels supported by the audio device.

Gets the state of the Mute node for the audio device channel.

Gets the PeakMeter value  for the audio device channel.

Gets the volume level for a given channel of the audio device.

Gets the audio data format for an audio device.

Gets the format type and the buffer size for the audio engine's audio data format.

Gets the state of the global effects (GFX) node in the audio engine.

Gets the audio data format for the audio engine mixer.

Gets the supported audio data formats for the audio device.

Sets the state of the Mute node for the audio device channel.

Sets the volume level for a given channel of the audio device.

Sets the audio data format for an audio device.

Sets the state of the global effects (GFX) node in the audio engine.

 


## -members
The <b>IMiniportAudioEngineNode</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265074">GetAudioEngineDescriptor</a>
</td>
<td align="left" width="63%">
Gets the descriptor for the audio engine node.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265075">GetBufferSizeRange</a>
</td>
<td align="left" width="63%">
Gets the minimum and maximum buffer size that the hardware audio engine can support.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265076">GetDeviceAttributeSteppings</a>
</td>
<td align="left" width="63%">
Gets the allowed stepping value for the audio device attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265077">GetDeviceChannelCount</a>
</td>
<td align="left" width="63%">
Gets a count of the number of channels supported by the audio device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265078">GetDeviceChannelMute</a>
</td>
<td align="left" width="63%">
Gets the state of the Mute node for the audio device channel.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265079">GetDeviceChannelPeakMeter</a>
</td>
<td align="left" width="63%">
Gets the PeakMeter value  for the audio device channel.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265080">GetDeviceChannelVolume</a>
</td>
<td align="left" width="63%">
Gets the volume level for a given channel of the audio device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265081">GetDeviceFormat</a>
</td>
<td align="left" width="63%">
Gets the audio data format for an audio device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265082">GetEngineFormatSize</a>
</td>
<td align="left" width="63%">
Gets the format type and the buffer size for the audio engine's audio data format.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265083">GetGfxState</a>
</td>
<td align="left" width="63%">
Gets the state of the global effects (GFX) node in the audio engine.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265084">GetMixFormat</a>
</td>
<td align="left" width="63%">
Gets the audio data format for the audio engine mixer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265085">GetSupportedDeviceFormats</a>
</td>
<td align="left" width="63%">
Gets the supported audio data formats for the audio device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265086">SetDeviceChannelMute</a>
</td>
<td align="left" width="63%">
Sets the state of the Mute node for the audio device channel.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265087">SetDeviceChannelVolume</a>
</td>
<td align="left" width="63%">
Sets the volume level for a given channel of the audio device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265088">SetDeviceFormat</a>
</td>
<td align="left" width="63%">
Sets the audio data format for an audio device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265089">SetGfxState</a>
</td>
<td align="left" width="63%">
Sets the state of the global effects (GFX) node in the audio engine.

</td>
</tr>
</table>Gets the descriptor for the audio engine node.

Gets the minimum and maximum buffer size that the hardware audio engine can support.

Gets the allowed stepping value for the audio device attribute.

Gets a count of the number of channels supported by the audio device.

Gets the state of the Mute node for the audio device channel.

Gets the PeakMeter value  for the audio device channel.

Gets the volume level for a given channel of the audio device.

Gets the audio data format for an audio device.

Gets the format type and the buffer size for the audio engine's audio data format.

Gets the state of the global effects (GFX) node in the audio engine.

Gets the audio data format for the audio engine mixer.

Gets the supported audio data formats for the audio device.

Sets the state of the Mute node for the audio device channel.

Sets the volume level for a given channel of the audio device.

Sets the audio data format for an audio device.

Sets the state of the global effects (GFX) node in the audio engine.

 


## -remarks
