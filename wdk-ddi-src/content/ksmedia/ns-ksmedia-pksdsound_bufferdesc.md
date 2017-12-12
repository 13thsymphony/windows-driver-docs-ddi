---
UID: NS.KSMEDIA.PKSDSOUND_BUFFERDESC
title: PKSDSOUND_BUFFERDESC
author: windows-driver-content
description: The KSDSOUND_BUFFERDESC structure describes a DirectSound buffer.
old-location: audio\ksdsound_bufferdesc.htm
old-project: audio
ms.assetid: 95b2f2ff-b98f-4210-9a4f-898573679aa7
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PKSDSOUND_BUFFERDESC, KSDSOUND_BUFFERDESC, *PKSDSOUND_BUFFERDESC
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
req.alt-api: KSDSOUND_BUFFERDESC
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
---

# PKSDSOUND_BUFFERDESC structure



## -description
The KSDSOUND_BUFFERDESC structure describes a DirectSound buffer.



## -syntax

````
typedef struct {
  ULONG        Flags;
  ULONG        Control;
  WAVEFORMATEX WaveFormatEx;
} KSDSOUND_BUFFERDESC, *PKSDSOUND_BUFFERDESC;
````


## -struct-fields

### -field Flags

Specifies the buffer configuration. This member can be set to the bitwise OR of one or more of the following flag bits:




### -field KSDSOUND_BUFFER_PRIMARY

Indicates that the buffer is a primary sound buffer (the buffer the user hears when a game is playing).


### -field KSDSOUND_BUFFER_STATIC

Indicates that the buffer will be used for static sound data.


### -field KSDSOUND_BUFFER_LOCHARDWARE

Forces the buffer to use hardware mixing.


### -field KSDSOUND_BUFFER_LOCSOFTWARE

Forces the buffer to be stored in system memory and use software mixing.

</dd>
</dl>

### -field Control

Specifies the capabilities of the buffer. The capabilities of a buffer are represented by a set of control flags. This member can be set to the bitwise OR of one or more of the following flag bits:




### -field KSDSOUND_BUFFER_CTRL_3D

Indicates that the buffer is either a primary buffer or a secondary buffer with 3D-control capability. If this bit is set, the KS pin representing the buffer implements a 3D node (<a href="https://msdn.microsoft.com/library/windows/hardware/ff537148">KSNODETYPE_3D_EFFECTS</a>). If the KSDSOUND_BUFFER_CTRL_HRTF_3D bit is set, the 3D node supports the optional <a href="https://msdn.microsoft.com/library/windows/hardware/ff537482">KSPROPSETID_Hrtf3d</a> property set.


### -field KSDSOUND_BUFFER_CTRL_FREQUENCY

Indicates that the buffer has frequency-control capability. If this bit is set, the pin representing the buffer implements a sample-rate conversion (<a href="https://msdn.microsoft.com/library/windows/hardware/ff537190">KSNODETYPE_SRC</a>) node.


### -field KSDSOUND_BUFFER_CTRL_HRTF_3D

Indicates that the buffer uses a head-related transfer function (HRTF) for 3D control. If this bit is set, then the KSDSOUND_BUFFER_CTRL_3D bit must also be set.


### -field KSDSOUND_BUFFER_CTRL_PAN

Indicates that the buffer has pan-control capability. If this bit is set, the pin representing the buffer implements a volume node (<a href="https://msdn.microsoft.com/library/windows/hardware/ff537208">KSNODETYPE_VOLUME</a>) to control panning. For more information, see <a href="https://msdn.microsoft.com/baca55f5-c669-4bd2-82b5-3985030864f2">DirectSound Node-Ordering Requirements</a>.


### -field KSDSOUND_BUFFER_CTRL_VOLUME

Indicates that the buffer has volume-control capability. If this bit is set, the pin representing the buffer implements a volume node (<a href="https://msdn.microsoft.com/library/windows/hardware/ff537208">KSNODETYPE_VOLUME</a>) to control the stream's volume level.


### -field KSDSOUND_BUFFER_CTRL_POSITIONNOTIFY

Indicates that the buffer has position-notification capability. If this bit is set, the pin representing the buffer supports the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537297">KSPROPERTY_AUDIO_POSITION</a> property.

</dd>
</dl>

### -field WaveFormatEx

Specifies the wave-data format of the buffer. This member is a structure of type <a href="audio.waveformatex">WAVEFORMATEX</a>.


## -remarks
The <a href="audio.ksdataformat_dsound">KSDATAFORMAT_DSOUND</a> structure contains a <b>BufferDesc</b> member that is a KSDSOUND_BUFFERDESC structure.

Note that the <b>WaveFormatEx</b> member of the KSDSOUND_BUFFERDESC structure can be extended to include additional format information (for example, a channel configuration mask). For details, see <a href="audio.waveformatextensible">WAVEFORMATEXTENSIBLE</a>.


## -requirements
<table>
<tr>
<th width="30%">
Header

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
<a href="audio.ksdataformat_dsound">KSDATAFORMAT_DSOUND</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537148">KSNODETYPE_3D_EFFECTS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537482">KSPROPSETID_Hrtf3d</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537190">KSNODETYPE_SRC</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537208">KSNODETYPE_VOLUME</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537297">KSPROPERTY_AUDIO_POSITION</a>
</dt>
<dt>
<a href="audio.waveformatex">WAVEFORMATEX</a>
</dt>
<dt>
<a href="audio.waveformatextensible">WAVEFORMATEXTENSIBLE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSDSOUND_BUFFERDESC structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

