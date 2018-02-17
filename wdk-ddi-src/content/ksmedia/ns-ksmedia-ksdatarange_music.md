---
UID: NS:ksmedia.KSDATARANGE_MUSIC
title: KSDATARANGE_MUSIC
author: windows-driver-content
description: The KSDATARANGE_MUSIC structure specifies a range of DirectMusic MIDI formats.
old-location: audio\ksdatarange_music.htm
old-project: audio
ms.assetid: 2ada5d1c-9c46-4f7b-99e5-72aa8f6fee9f
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: aud-prop_5c82e83d-000e-440e-bfcb-8daef30f5056.xml, PKSDATARANGE_MUSIC structure pointer [Audio Devices], ksmedia/PKSDATARANGE_MUSIC, audio.ksdatarange_music, *PKSDATARANGE_MUSIC, PKSDATARANGE_MUSIC, KSDATARANGE_MUSIC, ksmedia/KSDATARANGE_MUSIC, KSDATARANGE_MUSIC structure [Audio Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KSDATARANGE_MUSIC
product: Windows
targetos: Windows
req.typenames: "*PKSDATARANGE_MUSIC, KSDATARANGE_MUSIC"
---

# KSDATARANGE_MUSIC structure
The KSDATARANGE_MUSIC structure specifies a range of DirectMusic MIDI formats.

## Syntax
````
typedef struct {
  KSDATARANGE DataRange;
  GUID        Technology;
  ULONG       Channels;
  ULONG       Notes;
  ULONG       ChannelMask;
} KSDATARANGE_MUSIC, *PKSDATARANGE_MUSIC;
````

## Members


`ChannelMask`

Specifies which channels an internal synthesizer device responds to, where the least significant bit refers to channel 0 and the most significant bit to channel 15. Port devices that transmit on all channels set this member to 0xFFFF.

`Channels`

Specifies the maximum number of simultaneous channels that can be played by an internal synthesizer device. If the device is a port, this member is not meaningful and is set to zero.

`DataRange`

Specifies the MajorFormat and SubFormat GUIDs as well as the Specifier GUID for the DirectMusic data. This member is an initialized <a href="..\ks\ns-ks-ksdataformat.md">KSDATARANGE</a> structure.

`Notes`

Specifies the maximum number of simultaneous notes that can be played by an internal synthesizer device. If the device is a port, this member is not meaningful and is set to zero.

`Technology`

Specifies the type of MIDI output device. This member can be one of the following GUIDs:





#### KSMUSIC_TECHNOLOGY_PORT

The device is a MIDI hardware port.



#### KSMUSIC_TECHNOLOGY_SYNTH

The device is a synthesizer.



#### KSMUSIC_TECHNOLOGY_SQSYNTH

The device is a square-wave synthesizer.



#### KSMUSIC_TECHNOLOGY_FMSYNTH

The device is an FM synthesizer.



#### KSMUSIC_TECHNOLOGY_MAPPER

The device is the Microsoft MIDI mapper.



#### KSMUSIC_TECHNOLOGY_WAVETABLE

The device is a hardware wavetable synthesizer.



#### KSMUSIC_TECHNOLOGY_SWSYNTH

The device is a software synthesizer.

## Remarks
For examples of data ranges that use the KSDATARANGE_MUSIC structure, see <a href="https://msdn.microsoft.com/392eadf7-9c6e-4527-bc84-a2916623c154">MIDI Stream Data Range</a> and <a href="https://msdn.microsoft.com/e3423901-330e-4a86-a921-6678e1c45a97">DirectMusic Stream Data Range</a>.

For information about data ranges and intersection handling, see <a href="https://msdn.microsoft.com/7206afdb-8a34-4b5a-8cea-87119f426161">Data-Intersection Handlers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="..\ks\ns-ks-ksdataformat.md">KSDATARANGE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSDATARANGE_MUSIC structure%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>