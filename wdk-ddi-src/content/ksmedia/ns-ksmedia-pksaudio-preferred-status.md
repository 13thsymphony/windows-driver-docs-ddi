---
UID: NS.ksmedia.PKSAUDIO_PREFERRED_STATUS
title: PKSAUDIO_PREFERRED_STATUS
author: windows-driver-content
description: The KSAUDIO_PREFERRED_STATUS structure specifies the status of a preferred device.
old-location: audio\ksaudio_preferred_status.htm
ms.assetid: 3191aeff-7324-4c2b-9b64-ddc50a561df5
ms.author: windowsdriverdev
ms.date: 10/30/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: audio
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSAUDIO_PREFERRED_STATUS
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
ms.keywords: PKSAUDIO_PREFERRED_STATUS, KSAUDIO_PREFERRED_STATUS, *PKSAUDIO_PREFERRED_STATUS
req.iface: 
---

# PKSAUDIO_PREFERRED_STATUS structure



## -description
<p>The KSAUDIO_PREFERRED_STATUS structure specifies the status of a preferred device.</p>


## -syntax

````
typedef struct {
  BOOL                             Enable;
  KSPROPERTY_SYSAUDIO_DEFAULT_TYPE DeviceType;
  ULONG                            Flags;
  ULONG                            Reserved;
} KSAUDIO_PREFERRED_STATUS, *PKSAUDIO_PREFERRED_STATUS;
````


## -struct-fields
<dl>

### -field <b>Enable</b>

<dd>
<p>Specifies whether the target device is the new preferred device. If <b>TRUE</b>, the target device is selected as the new preferred device. If <b>FALSE</b>, the target device was previously the preferred device, but is now deselected.</p>
</dd>

### -field <b>DeviceType</b>

<dd>
<p>Specifies the type of preferred device. This parameter is set to one of the following constants:</p>
<table>
<tr>
<th>Value</th>
<th>Device type</th>
</tr>
<tr>
<td>
<p>KSPROPERTY_SYSAUDIO_NORMAL_DEFAULT</p>
</td>
<td>
<p>Preferred device for wave playback/recording, MIDI, and mixer topology.</p>
</td>
</tr>
<tr>
<td>
<p>KSPROPERTY_SYSAUDIO_PLAYBACK_DEFAULT</p>
</td>
<td>
<p>Preferred wave playback device.</p>
</td>
</tr>
<tr>
<td>
<p>KSPROPERTY_SYSAUDIO_RECORD_DEFAULT</p>
</td>
<td>
<p>Preferred wave recording device.</p>
</td>
</tr>
<tr>
<td>
<p>KSPROPERTY_SYSAUDIO_MIDI_DEFAULT</p>
</td>
<td>
<p>Preferred MIDI device.</p>
</td>
</tr>
<tr>
<td>
<p>KSPROPERTY_SYSAUDIO_MIXER_DEFAULT</p>
</td>
<td>
<p>Preferred mixer topology device.</p>
</td>
</tr>
</table>
<p> </p>
<p>The driver uses this member to determine what aspect or aspects of the audio adapter are currently selected as preferred. A driver might use this information to decide how to configure itself or decide what system resources to request.</p>
</dd>

### -field <b>Flags</b>

<dd>
<p>No flags are currently defined. Set to zero.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>Reserved for future use. Set to zero.</p>
</dd>
</dl>

## -remarks
<p>This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537299">KSPROPERTY_AUDIO_PREFERRED_STATUS</a> property.</p>

<p>For information about the preferred device, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff537899">SetupPreferredAudioDevices</a>.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537299">KSPROPERTY_AUDIO_PREFERRED_STATUS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537899">SetupPreferredAudioDevices</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAUDIO_PREFERRED_STATUS structure%20 RELEASE:%20(10/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
