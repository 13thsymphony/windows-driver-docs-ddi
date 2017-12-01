---
UID: NS.ksmedia.PKSPROPERTY_VIDEODECODER_STATUS_S
title: PKSPROPERTY_VIDEODECODER_STATUS_S
author: windows-driver-content
description: The KSPROPERTY_VIDEODECODER_STATUS_S structure describes the present status of a video decoding device, such as number of lines in the incoming analog signal and whether the signal is locked in.
old-location: stream\ksproperty_videodecoder_status_s.htm
old-project: stream
ms.assetid: 12b92834-dcab-4723-91e5-9b7ab0bdd719
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PKSPROPERTY_VIDEODECODER_STATUS_S, KSPROPERTY_VIDEODECODER_STATUS_S, *PKSPROPERTY_VIDEODECODER_STATUS_S
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
req.alt-api: KSPROPERTY_VIDEODECODER_STATUS_S
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

# PKSPROPERTY_VIDEODECODER_STATUS_S structure



## -description
<p>The KSPROPERTY_VIDEODECODER_STATUS_S structure describes the present status of a video decoding device, such as number of lines in the incoming analog signal and whether the signal is locked in.</p>


## -syntax

````
typedef struct {
  KSPROPERTY Property;
  ULONG      NumberOfLines;
  ULONG      SignalLocked;
} KSPROPERTY_VIDEODECODER_STATUS_S, *PKSPROPERTY_VIDEODECODER_STATUS_S;
````


## -struct-fields
<dl>

### -field <b>Property</b>

<dd>
<p>Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type.</p>
</dd>

### -field <b>NumberOfLines</b>

<dd>
<p>Indicates the number of lines detected in the incoming analog video signal.</p>
</dd>

### -field <b>SignalLocked</b>

<dd>
<p>Indicates whether the signal is locked. Zero indicates that the signal is not locked. A nonzero value indicates the signal is locked.</p>
</dd>
</dl>

## -remarks
<p>The KSPROPERTY_VIDEODECODER_STATUS_S structure retrieves information about the video decoding process, including the number of lines in the incoming analog video signal.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566060">KSPROPERTY_VIDEODECODER_STATUS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_VIDEODECODER_STATUS_S structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
