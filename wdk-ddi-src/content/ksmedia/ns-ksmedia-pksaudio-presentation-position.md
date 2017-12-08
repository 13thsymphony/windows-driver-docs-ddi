---
UID: NS.ksmedia.PKSAUDIO_PRESENTATION_POSITION
title: PKSAUDIO_PRESENTATION_POSITION
author: windows-driver-content
description: The KSAUDIO_PRESENTATION_POSITION structure specifies the current cursor position in audio data stream that is being rendered to the endpoint.
old-location: audio\ksaudio_presentation_position.htm
old-project: audio
ms.assetid: 6C9F2E99-17B4-49AD-A94F-E3EF9282B649
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PKSAUDIO_PRESENTATION_POSITION, KSAUDIO_PRESENTATION_POSITION, *PKSAUDIO_PRESENTATION_POSITION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSAUDIO_PRESENTATION_POSITION
req.alt-loc: Ksmedia.h
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

# PKSAUDIO_PRESENTATION_POSITION structure



## -description
<p>The <b>KSAUDIO_PRESENTATION_POSITION</b> structure specifies the current cursor position in audio data stream that is being rendered to the endpoint.</p>


## -syntax

````
typedef struct _KSAUDIO_PRESENTATION_POSITION {
  UINT64 u64PositionInBlocks;
  UINT64 u64QPCPosition;
} KSAUDIO_PRESENTATION_POSITION, *PKSAUDIO_PRESENTATION_POSITION;
````


## -struct-fields
<dl>

### -field u64PositionInBlocks

<dd>
<p>Specifies the block offset from the start of the stream to the current post-decoded, uncompressed position in the stream. A "block" refers to the group of channels in the same sample. So, for example, in a PCM stream a block is the same as a frame. However, for compressed formats a block is a single sample within a frame. This means that for a typical MP3 stream that has 1152 samples in a frame, there are 1152 blocks. </p>
</dd>

### -field u64QPCPosition

<dd>
<p>Specifies the value of the performance counter at the time that the audio driver reads the presentation position in response to the <b>KSAUDIO_PRESENTATION_POSITION</b> call. A driver writes to this field with the value read from calling <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff553053(v=vs.85).aspx">KeQueryPerformanceCounter</a> when a snapshot is taken of the presentation position.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ksmedia.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt><a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff553053(v=vs.85).aspx">KeQueryPerformanceCounter</a></dt>
<dt>
<a href="audio.ksaudio_presentation_position">KSAUDIO_PRESENTATION_POSITION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh450895">KSPROPERTY_AUDIO_PRESENTATION_POSITION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAUDIO_PRESENTATION_POSITION structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
