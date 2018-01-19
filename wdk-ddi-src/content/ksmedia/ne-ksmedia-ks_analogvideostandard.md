---
UID : NE:ksmedia.KS_AnalogVideoStandard
title : KS_AnalogVideoStandard
author : windows-driver-content
description : The KS_AnalogVideoStandard enumeration defines various analog video standards that are used worldwide.
old-location : stream\ks_analogvideostandard.htm
old-project : stream
ms.assetid : 33efef2f-0734-416e-9f89-394a3dd344b8
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KS_AnalogVideoStandard, KS_AnalogVideoStandard
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ksmedia.h
req.include-header : Ksmedia.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KS_AnalogVideoStandard
req.alt-loc : ksmedia.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : KS_AnalogVideoStandard
---

# KS_AnalogVideoStandard Enumeration
The KS_AnalogVideoStandard enumeration defines various analog video standards that are used worldwide.

## Syntax
````
typedef enum  { 
  KS_AnalogVideo_None         = 0x00000000,
  KS_AnalogVideo_NTSC_M       = 0x00000001,
  KS_AnalogVideo_NTSC_M_J     = 0x00000002,
  KS_AnalogVideo_NTSC_433     = 0x00000004,
  KS_AnalogVideo_PAL_B        = 0x00000010,
  KS_AnalogVideo_PAL_D        = 0x00000020,
  KS_AnalogVideo_PAL_G        = 0x00000040,
  KS_AnalogVideo_PAL_H        = 0x00000080,
  KS_AnalogVideo_PAL_I        = 0x00000100,
  KS_AnalogVideo_PAL_M        = 0x00000200,
  KS_AnalogVideo_PAL_N        = 0x00000400,
  KS_AnalogVideo_PAL_60       = 0x00000800,
  KS_AnalogVideo_SECAM_B      = 0x00001000,
  KS_AnalogVideo_SECAM_D      = 0x00002000,
  KS_AnalogVideo_SECAM_G      = 0x00004000,
  KS_AnalogVideo_SECAM_H      = 0x00008000,
  KS_AnalogVideo_SECAM_K      = 0x00010000,
  KS_AnalogVideo_SECAM_K1     = 0x00020000,
  KS_AnalogVideo_SECAM_L      = 0x00040000,
  KS_AnalogVideo_SECAM_L1     = 0x00080000,
  KS_AnalogVideo_PAL_N_COMBO  = 0x00100000
} KS_AnalogVideoStandard;
````

## Constants

<table>

<tr>
<td>KS_AnalogVideo_None</td>
<td>Specifies a digital sensor.</td>
</tr>

<tr>
<td>KS_AnalogVideo_NTSC_433</td>
<td>Specifies the NTSC 433 standard</td>
</tr>

<tr>
<td>KS_AnalogVideo_NTSC_M</td>
<td>Specifies the National Television Standards Committee (NTSC) "M" standard, at 7.5 IRE for black.</td>
</tr>

<tr>
<td>KS_AnalogVideo_NTSC_M_J</td>
<td>Specifies the NTSC "M" standard that is used in Japan, at 0 IRE for black.</td>
</tr>

<tr>
<td>KS_AnalogVideo_PAL_60</td>
<td>Specifies the PAL-60 standard.</td>
</tr>

<tr>
<td>KS_AnalogVideo_PAL_B</td>
<td>Specifies the Phase Alteration Line (PAL) "B" standard.</td>
</tr>

<tr>
<td>KS_AnalogVideo_PAL_D</td>
<td>Specifies the PAL "D" standard.</td>
</tr>

<tr>
<td>KS_AnalogVideo_PAL_G</td>
<td>Specifies the PAL "G" standard.</td>
</tr>

<tr>
<td>KS_AnalogVideo_PAL_H</td>
<td>Specifies the PAL "H" standard.</td>
</tr>

<tr>
<td>KS_AnalogVideo_PAL_I</td>
<td>Specifies the PAL "I" standard.</td>
</tr>

<tr>
<td>KS_AnalogVideo_PAL_M</td>
<td>Specifies the PAL "M" standard.</td>
</tr>

<tr>
<td>KS_AnalogVideo_PAL_N</td>
<td>Specifies the PAL "N" standard.</td>
</tr>

<tr>
<td>KS_AnalogVideo_PAL_N_COMBO</td>
<td>Specifies the combination PAL "N" standard (Argentina).</td>
</tr>

<tr>
<td>KS_AnalogVideo_SECAM_B</td>
<td>Specifies the Systeme Electronic Pour Couleur Avec Memoire (SECAM) "B" standard.</td>
</tr>

<tr>
<td>KS_AnalogVideo_SECAM_D</td>
<td>Specifies the SECAM "D" standard.</td>
</tr>

<tr>
<td>KS_AnalogVideo_SECAM_G</td>
<td>Specifies the SECAM "G" standard.</td>
</tr>

<tr>
<td>KS_AnalogVideo_SECAM_H</td>
<td>Specifies the SECAM "H" standard.</td>
</tr>

<tr>
<td>KS_AnalogVideo_SECAM_K</td>
<td>Specifies the SECAM "K" standard.</td>
</tr>

<tr>
<td>KS_AnalogVideo_SECAM_K1</td>
<td>Specifies the SECAM "K1" standard.</td>
</tr>

<tr>
<td>KS_AnalogVideo_SECAM_L</td>
<td>Specifies the SECAM "L" standard.</td>
</tr>

<tr>
<td>KS_AnalogVideo_SECAM_L1</td>
<td>Specifies the SECAM "L1" standard.</td>
</tr>
</table>

## Remarks

You can combine the values in the KS_AnalogVideoStandard enumeration with a bitwise OR  indicate support for multiple analog video standards.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<dl>
<dt>
<a href="..\ksmedia\ns-ksmedia-tagks_tvtuner_change_info.md">KS_TVTUNER_CHANGE_INFO</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-tagks_vbiinfoheader.md">KS_VBIINFOHEADER</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-_ks_video_stream_config_caps.md">KS_VIDEO_STREAM_CONFIG_CAPS</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-ksproperty_tuner_mode_caps_s.md">KSPROPERTY_TUNER_MODE_CAPS_S</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-ksproperty_tuner_standard_s.md">KSPROPERTY_TUNER_STANDARD_S</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-ksproperty_videodecoder_caps_s.md">KSPROPERTY_VIDEODECODER_CAPS_S</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_AnalogVideoStandard enumeration%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>