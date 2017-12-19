---
UID: NS.HDAUDIO._HDAUDIO_STREAM_FORMAT
title: _HDAUDIO_STREAM_FORMAT
author: windows-driver-content
description: The HDAUDIO_STREAM_FORMAT structure describes the data format of a capture or render stream.
old-location: audio\hdaudio_stream_format.htm
old-project: audio
ms.assetid: 475b7774-51ce-410d-aba8-a2317f44ce03
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _HDAUDIO_STREAM_FORMAT, *PHDAUDIO_STREAM_FORMAT, PHDAUDIO_STREAM_FORMAT, HDAUDIO_STREAM_FORMAT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HDAUDIO_STREAM_FORMAT
req.alt-loc: hdaudio.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL.
---

# _HDAUDIO_STREAM_FORMAT structure



## -description
The HDAUDIO_STREAM_FORMAT structure describes the data format of a capture or render stream.



## -syntax

````
typedef struct _HDAUDIO_STREAM_FORMAT {
  ULONG  SampleRate;
  USHORT ValidBitsPerSample;
  USHORT ContainerSize;
  USHORT NumberOfChannels;
} HDAUDIO_STREAM_FORMAT, *PHDAUDIO_STREAM_FORMAT;
````


## -struct-fields

### -field SampleRate

Specifies the sample rate in samples per second. This member indicates the rate at which each channel should be played or recorded.


### -field ValidBitsPerSample

Specifies the number of valid bits per sample. The valid bits are left justified within the container. Any unused bits to the right of the valid bits must be set to zero.


### -field ContainerSize

Specifies the size in bits of a sample container. Valid values for this member are 8, 16, 24, and 32.


### -field NumberOfChannels

Specifies the number of channels of audio data. For monophonic audio, set this member to 1. For stereo, set this member to 2.


## -remarks
The <a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a>, <a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>, and <a href="..\hdaudio\nc-hdaudio-pchange_bandwidth_allocation.md">ChangeBandwidthAllocation</a> routines take as an input parameter an HDAUDIO_STREAM_FORMAT structure and output the corresponding <a href="audio.hdaudio_converter_format">HDAUDIO_CONVERTER_FORMAT</a> structure. The information in a valid HDAUDIO_STREAM_FORMAT value can be encoded as an HDAUDIO_CONVERTER_FORMAT value.

This structure is similar to the <a href="..\ksmedia\ns-ksmedia-waveformatextensible.md">WAVEFORMATEXTENSIBLE</a> structure, but it omits certain parameters that are in WAVEFORMATEXTENSIBLE but are not relevant to the task of managing codecs that are connected to an HD Audio controller.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hdaudio.h (include Hdaudio.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\hdaudio\nc-hdaudio-pallocate_capture_dma_engine.md">AllocateCaptureDmaEngine</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pallocate_render_dma_engine.md">AllocateRenderDmaEngine</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pchange_bandwidth_allocation.md">ChangeBandwidthAllocation</a>
</dt>
<dt>
<a href="audio.hdaudio_converter_format">HDAUDIO_CONVERTER_FORMAT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20HDAUDIO_STREAM_FORMAT structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

