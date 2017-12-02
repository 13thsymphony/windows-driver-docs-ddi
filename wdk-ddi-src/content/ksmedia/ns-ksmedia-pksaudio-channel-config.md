---
UID: NS.ksmedia.PKSAUDIO_CHANNEL_CONFIG
title: PKSAUDIO_CHANNEL_CONFIG
author: windows-driver-content
description: The KSAUDIO_CHANNEL_CONFIG structure specifies the configuration of channels within the data format of an audio stream.
old-location: audio\ksaudio_channel_config.htm
old-project: audio
ms.assetid: 64e46fd5-f6bf-425d-b2a5-c938f8e565b9
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PKSAUDIO_CHANNEL_CONFIG, KSAUDIO_CHANNEL_CONFIG, *PKSAUDIO_CHANNEL_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSAUDIO_CHANNEL_CONFIG
req.alt-loc: ksmedia.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: 
---

# PKSAUDIO_CHANNEL_CONFIG structure



## -description
<p>The KSAUDIO_CHANNEL_CONFIG structure specifies the configuration of channels within the data format of an audio stream.</p>


## -syntax

````
typedef struct {
  LONG ActiveSpeakerPositions;
} KSAUDIO_CHANNEL_CONFIG, *PKSAUDIO_CHANNEL_CONFIG;
````


## -struct-fields
<dl>

### -field ActiveSpeakerPositions

<dd>
<p>Specifies both the number of channels and the assignment of those channels to speaker positions. This member is a bitmask in which each bit within the mask corresponds to a particular speaker position. If a mask bit is set, the audio stream contains a channel that is assigned to the speaker position that the mask bit represents. The number of channels in the stream is obtained by counting how many number ones appear in the bitmask. For more information, see the following Remarks section.</p>
</dd>
</dl>

## -remarks
<p>This structure is used to set or get the data value for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537250">KSPROPERTY_AUDIO_CHANNEL_CONFIG</a> property.</p>

<p>The following table shows the flag bits that are defined for the <b>ActiveSpeakerPositions</b> member.</p>

<p>SPEAKER_FRONT_LEFT</p>

<p>0x1</p>

<p>SPEAKER_FRONT_RIGHT</p>

<p>0x2</p>

<p>SPEAKER_FRONT_CENTER</p>

<p>0x4</p>

<p>SPEAKER_LOW_FREQUENCY</p>

<p>0x8</p>

<p>SPEAKER_BACK_LEFT</p>

<p>0x10</p>

<p>SPEAKER_BACK_RIGHT</p>

<p>0x20</p>

<p>SPEAKER_FRONT_LEFT_OF_CENTER</p>

<p>0x40</p>

<p>SPEAKER_FRONT_RIGHT_OF_CENTER</p>

<p>0x80</p>

<p>SPEAKER_BACK_CENTER</p>

<p>0x100</p>

<p>SPEAKER_SIDE_LEFT</p>

<p>0x200</p>

<p>SPEAKER_SIDE_RIGHT</p>

<p>0x400</p>

<p>SPEAKER_TOP_CENTER</p>

<p>0x800</p>

<p>SPEAKER_TOP_FRONT_LEFT</p>

<p>0x1000</p>

<p>SPEAKER_TOP_FRONT_CENTER</p>

<p>0x2000</p>

<p>SPEAKER_TOP_FRONT_RIGHT</p>

<p>0x4000</p>

<p>SPEAKER_TOP_BACK_LEFT</p>

<p>0x8000</p>

<p>SPEAKER_TOP_BACK_CENTER</p>

<p>0x10000</p>

<p>SPEAKER_TOP_BACK_RIGHT</p>

<p>0x20000</p>

<p>Each audio data format contains channels for one or more of the preceding speaker positions. The number of channels simply equals the number of nonzero flag bits in the <b>ActiveSpeakerPositions</b> member.</p>

<p>The relative positions of the channels within each block of audio data always follow the same relative ordering as the flag bits in the preceding table. For example, if <b>ActiveSpeakerPositions</b> contains the value 0x00000033, the format defines four audio channels that are assigned for playback to the front-left, front-right, back-left, and back-right speakers, respectively. The channel data should be interleaved in that order within each block. (This is the KSAUDIO_SPEAKER_QUAD configuration that appears in the second of the two following tables.)</p>

<p>The following table shows the speaker configurations that are defined for DVD.</p>

<p>KSAUDIO_SPEAKER_GROUND_FRONT_LEFT</p>

<p>KSAUDIO_SPEAKER_GROUND_FRONT_CENTER</p>

<p>KSAUDIO_SPEAKER_GROUND_FRONT_RIGHT</p>

<p>KSAUDIO_SPEAKER_GROUND_REAR_LEFT</p>

<p>KSAUDIO_SPEAKER_GROUND_REAR_RIGHT</p>

<p>KSAUDIO_SPEAKER_TOP_MIDDLE</p>

<p>KSAUDIO_SPEAKER_SUPER_WOOFER</p>

<p>The following table shows the speaker configurations that are defined for DirectSound.</p>

<p>KSAUDIO_SPEAKER_DIRECTOUT</p>

<p>0 (no speakers)</p>

<p>KSAUDIO_SPEAKER_MONO</p>

<p>(SPEAKER_FRONT_CENTER)</p>

<p>KSAUDIO_SPEAKER_STEREO</p>

<p>(SPEAKER_FRONT_LEFT | SPEAKER_FRONT_RIGHT)</p>

<p>KSAUDIO_SPEAKER_QUAD</p>

<p>(SPEAKER_FRONT_LEFT | SPEAKER_FRONT_RIGHT | SPEAKER_BACK_LEFT | SPEAKER_BACK_RIGHT)</p>

<p>KSAUDIO_SPEAKER_SURROUND</p>

<p>(SPEAKER_FRONT_LEFT | SPEAKER_FRONT_RIGHT | SPEAKER_FRONT_CENTER | SPEAKER_BACK_CENTER)</p>

<p>KSAUDIO_SPEAKER_5POINT1</p>

<p>(SPEAKER_FRONT_LEFT | SPEAKER_FRONT_RIGHT | SPEAKER_FRONT_CENTER | SPEAKER_LOW_FREQUENCY | SPEAKER_BACK_LEFT | SPEAKER_BACK_RIGHT)</p>

<p>KSAUDIO_SPEAKER_5POINT1_SURROUND</p>

<p>(SPEAKER_FRONT_LEFT | SPEAKER_FRONT_RIGHT |</p>

<p>SPEAKER_FRONT_CENTER | SPEAKER_LOW_FREQUENCY |</p>

<p>SPEAKER_SIDE_LEFT  | SPEAKER_SIDE_RIGHT)</p>

<p>KSAUDIO_SPEAKER_7POINT1</p>

<p>(SPEAKER_FRONT_LEFT | SPEAKER_FRONT_RIGHT | SPEAKER_FRONT_CENTER | SPEAKER_LOW_FREQUENCY | SPEAKER_BACK_LEFT | SPEAKER_BACK_RIGHT | SPEAKER_FRONT_LEFT_OF_CENTER | SPEAKER_FRONT_RIGHT_OF_CENTER)</p>

<p>KSAUDIO_SPEAKER_7POINT1_SURROUND</p>

<p>SPEAKER_BACK_LEFT | SPEAKER_BACK_RIGHT |</p>

<p>SPEAKER_SIDE_LEFT | SPEAKER_SIDE_RIGHT)</p>

<p>In the preceding table, the constant KSAUDIO_SPEAKER_DIRECTOUT has a value of zero, which means that no speaker positions are assigned to the channels in the multichannel stream. For example, channel zero might represent percussion, channel 1 might represent trumpet, channel 2 might represent voice, and so on. In this configuration, the channels in the input stream are output directly to the hardware without modification and without being interpreted as speaker positions. For more information, see <a href="https://msdn.microsoft.com/a4198fb7-157f-40e3-8cca-5a9e392087d2">DSSPEAKER_DIRECTOUT Speaker Configuration</a>.</p>

<p>The speaker configuration for a 5.1-channel surround format is defined by the constant KSAUDIO_SPEAKER_5POINT1_SURROUND in the preceding table. The geometric layout of the speakers is shown in the following figure, which shows the positions of the front-left, front-right, front-center, side-left, and side-right speakers. The figure omits the low-frequency speaker because it is nondirectional.</p>

<p>For this example, the following list shows the ordering of the six channels within each block of audio data:</p>

<p>For a PCM format with a 16-bit sample size, each block of audio data occupies 12 bytes, which are ordered as shown in the following table.</p>

<p>0</p>

<p>Front Left (8 LSBs)</p>

<p>1</p>

<p>Front Left (8 MSBs)</p>

<p>2</p>

<p>Front Right (8 LSBs)</p>

<p>3</p>

<p>Front Right (8 MSBs)</p>

<p>4</p>

<p>Front Center (8 LSBs)</p>

<p>5</p>

<p>Front Center (8 MSBs)</p>

<p>6</p>

<p>Low Freq (8 LSBs)</p>

<p>7</p>

<p>Low Freq (8 MSBs)</p>

<p>8</p>

<p>Side Left (8 LSBs)</p>

<p>9</p>

<p>Side Left (8 MSBs)</p>

<p>10</p>

<p>Side Right (8 LSBs)</p>

<p>11</p>

<p>Side Right (8 MSBs)</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ksmedia.h (include Ksmedia.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537250">KSPROPERTY_AUDIO_CHANNEL_CONFIG</a>
</dt>
<dt>
<a href="audio.waveformatextensible">WAVEFORMATEXTENSIBLE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAUDIO_CHANNEL_CONFIG structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
