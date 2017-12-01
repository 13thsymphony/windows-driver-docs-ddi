---
UID: NS.ksmedia.PKSAUDIO_COPY_PROTECTION
title: PKSAUDIO_COPY_PROTECTION
author: windows-driver-content
description: The KSAUDIO_COPY_PROTECTION structure specifies the copy-protection status of an audio stream.
old-location: audio\ksaudio_copy_protection.htm
old-project: audio
ms.assetid: 7dab0240-67c3-4412-a7a5-bb98d84c6bdd
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PKSAUDIO_COPY_PROTECTION, KSAUDIO_COPY_PROTECTION, *PKSAUDIO_COPY_PROTECTION
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
req.alt-api: KSAUDIO_COPY_PROTECTION
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

# PKSAUDIO_COPY_PROTECTION structure



## -description
<p>The KSAUDIO_COPY_PROTECTION structure specifies the copy-protection status of an audio stream.</p>


## -syntax

````
typedef struct {
  BOOL fCopyrighted;
  BOOL fOriginal;
} KSAUDIO_COPY_PROTECTION, *PKSAUDIO_COPY_PROTECTION;
````


## -struct-fields
<dl>

### -field <b>fCopyrighted</b>

<dd>
<p>Indicates whether the stream is copyrighted. If <b>TRUE</b>, the stream is copyrighted. If <b>FALSE</b>, the stream is not copyrighted and is not subject to copy protection.</p>
</dd>

### -field <b>fOriginal</b>

<dd>
<p>Indicates whether the stream is an original, first-generation copy of a stream or a second-generation copy of the original. If <b>TRUE</b>, the stream is original. If <b>FALSE</b>, it is a second-generation copy.</p>
</dd>
</dl>

## -remarks
<p>The <a href="https://msdn.microsoft.com/library/windows/hardware/ff537253">KSPROPERTY_AUDIO_COPY_PROTECTION</a> property uses this structure to report whether a stream is copyrighted, and also whether the stream is an original stream or a copy of the original stream.</p>

<p>An audio device that supports copy protection can use copyright and copy-generation information about a stream to prevent unlimited copying of proprietary audio content. For example, the Serial Copy Management System (SCMS) defines one level of copy protection that allows copying of an original, first-generation copy of a stream, but prevents copying of second-generation copies of the stream.</p>

<p>The KSPROPERTY_AUDIO_COPY_PROTECTION property is separate from and unrelated to the implementation of <a href="https://msdn.microsoft.com/7ce19196-5180-421f-b6be-ac4a235a8c16">Digital Rights Management (DRM)</a> and the Secure Audio Path (SAP) for Windows Media. For information about SAP, see the Microsoft Windows SDK documentation.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537253">KSPROPERTY_AUDIO_COPY_PROTECTION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAUDIO_COPY_PROTECTION structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
