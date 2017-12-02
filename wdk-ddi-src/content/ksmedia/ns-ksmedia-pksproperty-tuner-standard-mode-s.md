---
UID: NS.ksmedia.PKSPROPERTY_TUNER_STANDARD_MODE_S
title: PKSPROPERTY_TUNER_STANDARD_MODE_S
author: windows-driver-content
description: The KSPROPERTY_TUNER_STANDARD_MODE_S structure describes whether the tuning device can identify the tuner standard from the signal itself.
old-location: stream\ksproperty_tuner_standard_mode_s.htm
old-project: stream
ms.assetid: 5f725332-155d-484f-8eaf-b45e0d7413e7
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PKSPROPERTY_TUNER_STANDARD_MODE_S, KSPROPERTY_TUNER_STANDARD_MODE_S, *PKSPROPERTY_TUNER_STANDARD_MODE_S
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSPROPERTY_TUNER_STANDARD_MODE_S
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

# PKSPROPERTY_TUNER_STANDARD_MODE_S structure



## -description
<p>The KSPROPERTY_TUNER_STANDARD_MODE_S structure describes whether the tuning device can identify the tuner standard from the signal itself.</p>


## -syntax

````
typedef struct {
  KSPROPERTY Property;
  BOOL       AutoDetect;
} KSPROPERTY_TUNER_STANDARD_MODE_S, *PKSPROPERTY_TUNER_STANDARD_MODE_S;
````


## -struct-fields
<dl>

### -field Property

<dd>
<p>Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type.</p>
</dd>

### -field AutoDetect

<dd>
<p>A Boolean value that indicates whether the tuning device can automatically detect the tuner standard from the signal. <b>TRUE</b> indicates that the tuning device can automatically detect the tuner standard from the signal. <b>FALSE</b> indicates that the tuning device cannot automatically detect the tuner standard. </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the operating system.</p>
</td>
</tr>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565909">KSPROPERTY_TUNER_STANDARD_MODE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567800">PROPSETID_TUNER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_TUNER_STANDARD_MODE_S structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
