---
UID: NS.ksmedia.PSYSAUDIO_INSTANCE_INFO
title: PSYSAUDIO_INSTANCE_INFO
author: windows-driver-content
description: The SYSAUDIO_INSTANCE_INFO structure specifies which virtual audio device to open and includes flags for configuring that device.
old-location: audio\sysaudio_instance_info.htm
old-project: audio
ms.assetid: 3468b29d-e62c-46b4-b95e-06df846ebd81
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PSYSAUDIO_INSTANCE_INFO, SYSAUDIO_INSTANCE_INFO, *PSYSAUDIO_INSTANCE_INFO
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
req.alt-api: SYSAUDIO_INSTANCE_INFO
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

# PSYSAUDIO_INSTANCE_INFO structure



## -description
<p>The SYSAUDIO_INSTANCE_INFO structure specifies which virtual audio device to open and includes flags for configuring that device.</p>


## -syntax

````
typedef struct {
  KSPROPERTY Property;
  ULONG      Flags;
  ULONG      DeviceNumber;
} SYSAUDIO_INSTANCE_INFO, *PSYSAUDIO_INSTANCE_INFO;
````


## -struct-fields
<dl>

### -field <b>Property</b>

<dd>
<p>Specifies the property. This parameter is a structure of type <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>.</p>
</dd>

### -field <b>Flags</b>

<dd>
<p>Flags specifying how to configure the virtual audio device. Currently, the only flag bit defined for this parameter is SYSAUDIO_FLAGS_DONT_COMBINE_PINS. If set, this flag bit instructs SysAudio not to combine rendering pins. For more information, see the following Remarks section.</p>
</dd>

### -field <b>DeviceNumber</b>

<dd>
<p>Specifies the device ID. This member identifies the virtual audio device that is to be opened by the property request. If SysAudio enumerates <i>N</i> virtual audio devices (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff537419">KSPROPERTY_SYSAUDIO_DEVICE_COUNT</a>), the valid device IDs range from 0 to <i>N</i>-1.</p>
</dd>
</dl>

## -remarks
<p>This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537427">KSPROPERTY_SYSAUDIO_INSTANCE_INFO</a> property.</p>

<p>By default, a virtual audio device combines its wave-rendering pins. The SYSAUDIO_FLAGS_DONT_COMBINE_PINS flag overrides this default.</p>

<p>When pins are combined, the virtual audio device exposes a single pin factory that combines hardware-accelerated rendering pins on the audio device with software-emulated mixer pins on the <a href="audio.kernel_mode_wdm_audio_components#kmixer_system_driver#kmixer_system_driver">KMixer system driver</a>. If the pins are not combined, then hardware-accelerated pins and software-emulated pins are exposed through separate pin factories. In order to correctly report the number of hardware-accelerated pins to application programs, DirectSound requires that the pins not be combined.</p>

<p>This property is similar to <a href="https://msdn.microsoft.com/library/windows/hardware/ff537423">KSPROPERTY_SYSAUDIO_DEVICE_INSTANCE</a>, with the exception that it includes flags specifying how to configure the virtual audio device.</p>

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
<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537419">KSPROPERTY_SYSAUDIO_DEVICE_COUNT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537427">KSPROPERTY_SYSAUDIO_INSTANCE_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537423">KSPROPERTY_SYSAUDIO_DEVICE_INSTANCE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20SYSAUDIO_INSTANCE_INFO structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
