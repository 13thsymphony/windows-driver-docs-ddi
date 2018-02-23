---
UID: NS:ksmedia.KSAUDIO_MIX_CAPS
title: KSAUDIO_MIX_CAPS
author: windows-driver-content
description: The KSAUDIO_MIX_CAPS structure specifies the mixing capabilities of a particular data path from one input channel of a supermixer node (KSNODETYPE_SUPERMIX) to an output channel of the same node.
old-location: audio\ksaudio_mix_caps.htm
old-project: audio
ms.assetid: d201fdce-ae56-4ba5-a947-e3e0cecc6e17
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: KSAUDIO_MIX_CAPS, audio.ksaudio_mix_caps, *PKSAUDIO_MIX_CAPS, KSAUDIO_MIX_CAPS structure [Audio Devices], ksmedia/KSAUDIO_MIX_CAPS, PKSAUDIO_MIX_CAPS structure pointer [Audio Devices], PKSAUDIO_MIX_CAPS, aud-prop_5468df9e-d7f4-4449-a59f-694100f2f825.xml, ksmedia/PKSAUDIO_MIX_CAPS
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
-	KSAUDIO_MIX_CAPS
product: Windows
targetos: Windows
req.typenames: "*PKSAUDIO_MIX_CAPS, KSAUDIO_MIX_CAPS"
---

# KSAUDIO_MIX_CAPS structure
The KSAUDIO_MIX_CAPS structure specifies the mixing capabilities of a particular data path from one input channel of a supermixer node (<a href="https://msdn.microsoft.com/library/windows/hardware/ff537198">KSNODETYPE_SUPERMIX</a>) to an output channel of the same node. An array of these structures is used by a <a href="..\ksmedia\ns-ksmedia-ksaudio_mixcap_table.md">KSAUDIO_MIXCAP_TABLE</a> structure to specify the mixing capabilities for all such paths through a supermixer node.

## Syntax
````
typedef struct {
  BOOL  Mute;
  LONG  Minimum;
  LONG  Maximum;
  union {
    LONG Reset;
    LONG Resolution;
  };
} KSAUDIO_MIX_CAPS, *PKSAUDIO_MIX_CAPS;
````

## Members


`Maximum`

Specifies the maximum mix level for the data path from the input channel to the output channel. For more information, see the following Remarks section.

`Minimum`

Specifies the minimum mix level for the data path from the input channel to the output channel. For more information, see the following Remarks section.

`Mute`

Specifies whether the data path from the input channel to the output channel is muted (not mixed). A value of <b>TRUE</b> indicates that the data path is muted.

## Remarks
The mix-level values for the <b>Maximum</b> and <b>Minimum</b> members use the following scale:

-2147483648 is -Infinity decibels (attenuation), 

 -2147483647 is -32767.99998474 decibels (attenuation), and

+2147483647 is +32767.99998474 decibels (gain).

A decibel range represented by integer values -2147483648 to +2147483647, where 

This scale has a resolution of 1/65536 decibel.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537198">KSNODETYPE_SUPERMIX</a>



<a href="..\ksmedia\ns-ksmedia-ksaudio_mixcap_table.md">KSAUDIO_MIXCAP_TABLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537291">KSPROPERTY_AUDIO_MIX_LEVEL_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537292">KSPROPERTY_AUDIO_MIX_LEVEL_TABLE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAUDIO_MIX_CAPS structure%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>