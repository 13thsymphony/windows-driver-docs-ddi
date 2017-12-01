---
UID: NS.ksmedia.tagKSCAMERA_EXTENDEDPROP_FIELDOFVIEW
title: tagKSCAMERA_EXTENDEDPROP_FIELDOFVIEW
author: windows-driver-content
description: The Field of View Control property describes the current Field of View (FOV) of the camera along with the pitch angle of the camera position.
old-location: stream\kscamera_extendedprop_fieldofview.htm
old-project: stream
ms.assetid: CC3FFC63-8404-4EA6-9738-F0A3C52585B8
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: tagKSCAMERA_EXTENDEDPROP_FIELDOFVIEW, KSCAMERA_EXTENDEDPROP_FIELDOFVIEW, *PKSCAMERA_EXTENDEDPROP_FIELDOFVIEW
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSCAMERA_EXTENDEDPROP_FIELDOFVIEW
req.alt-loc: Ksmedia.h
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

# tagKSCAMERA_EXTENDEDPROP_FIELDOFVIEW structure



## -description
<p>The <i>Field of View Control</i> property describes the current Field of View (FOV) of the camera along with the pitch angle of the camera position.</p>


## -syntax

````
typedef struct _KSCAMERA_EXTENDEDPROP_FIELDOFVIEW {
  ULONG NormalizedFocalLengthX;
  ULONG NormalizedFocalLengthY;
  ULONG Flag;
  ULONG Reserved;
} KSCAMERA_EXTENDEDPROP_FIELDOFVIEW, *PKSCAMERA_EXTENDEDPROP_FIELDOFVIEW;
````


## -struct-fields
<dl>

### -field <b>NormalizedFocalLengthX</b>

<dd>
<p>The horizontal focal length, in millimeters, normalized to a 35mm camera aperture size.</p>
</dd>

### -field <b>NormalizedFocalLengthY</b>

<dd>
<p>The vertical focal length, in millimeters, normalized to a 35mm camera aperture size.</p>
</dd>

### -field <b>Flag</b>

<dd>
<p>Reserved. Set to 0.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>Reserved. Set to 0.</p>
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
<p>Available starting with Windows 8.1.</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/dn567574">KSPROPERTY_CAMERACONTROL_EXTENDED_FIELDOFVIEW</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSCAMERA_EXTENDEDPROP_FIELDOFVIEW structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
