---
UID: NS:ksmedia.KSAC3_ALTERNATE_AUDIO
title: KSAC3_ALTERNATE_AUDIO
author: windows-driver-content
description: The KSAC3_ALTERNATE_AUDIO structure specifies whether the two mono channels in an AC-3-encoded stream should be interpreted as a stereo pair or as two independent program channels.
old-location: audio\ksac3_alternate_audio.htm
old-project: audio
ms.assetid: 9b97deb9-7e64-49a1-8278-08084c8b7c84
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: "*PKSAC3_ALTERNATE_AUDIO, KSAC3_ALTERNATE_AUDIO, KSAC3_ALTERNATE_AUDIO structure [Audio Devices], PKSAC3_ALTERNATE_AUDIO, PKSAC3_ALTERNATE_AUDIO structure pointer [Audio Devices], aud-prop_172c7e1b-4c53-4836-82c2-37590cf87744.xml, audio.ksac3_alternate_audio, ksmedia/KSAC3_ALTERNATE_AUDIO, ksmedia/PKSAC3_ALTERNATE_AUDIO"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KSAC3_ALTERNATE_AUDIO
product: Windows
targetos: Windows
req.typenames: KSAC3_ALTERNATE_AUDIO, *PKSAC3_ALTERNATE_AUDIO
---

# KSAC3_ALTERNATE_AUDIO structure
The KSAC3_ALTERNATE_AUDIO structure specifies whether the two mono channels in an AC-3-encoded stream should be interpreted as a stereo pair or as two independent program channels.

## Syntax
```
typedef struct KSAC3_ALTERNATE_AUDIO {
  BOOL  fStereo;
  ULONG DualMode;
}  *PKSAC3_ALTERNATE_AUDIO;
```

## Members


`fStereo`

Specifies whether the two mono channels should be interpreted as a stereo pair. If <b>TRUE</b>, the two mono channels are treated as a stereo pair. If <b>FALSE</b>, <b>DualMode</b>=0x03 causes the two mono channels to be mixed before being output by the decoder.

`DualMode`

When two independent channels of audio are encoded in the stream, this member specifies whether to use the audio track in channel 1, channel 2, or both. A value of 0x01 selects channel 1, 0x02 selects channel 2, and 0x03 selects both. Specify the value of this member as one of the following constants:

<table>
<tr>
<th>Constant name</th>
<th>Value</th>
</tr>
<tr>
<td>
KSAC3_ALTERNATE_AUDIO_1

</td>
<td>
0x01

</td>
</tr>
<tr>
<td>
KSAC3_ALTERNATE_AUDIO_2

</td>
<td>
0x02

</td>
</tr>
<tr>
<td>
KSAC3_ALTERNATE_AUDIO_BOTH

</td>
<td>
0x03

</td>
</tr>
</table>

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537210">KSPROPERTY_AC3_ALTERNATE_AUDIO</a> property.

For more information about the encoding of AC-3 program channels, see the AC-3 specification at the <a href="http://go.microsoft.com/fwlink/p/?linkid=8730">Dolby Laboratories</a> website. The specification is titled Digital Audio Compression Standard (AC-3).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537210">KSPROPERTY_AC3_ALTERNATE_AUDIO</a>