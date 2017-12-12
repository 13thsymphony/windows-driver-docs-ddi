---
UID: NS.KSMEDIA.PKSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S
title: PKSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S
author: windows-driver-content
description: Describes video stabilization control properties in the PROPSETID_VIDCAP_CAMERACONTROL_VIDEO_STABILIZATION camera control property set. This structure specifies property values that are used in requests to the camera driver.
old-location: stream\ksproperty_cameracontrol_videostabilization_mode_s.htm
old-project: stream
ms.assetid: 7cbf015c-4756-4d5c-a5fb-9cd8a5e0e3fd
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PKSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S, *PKSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S, KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S
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
---

# PKSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S structure



## -description
Describes video stabilization control properties in the <b>PROPSETID_VIDCAP_CAMERACONTROL_VIDEO_STABILIZATION</b> camera control property set. This structure specifies property values that are used in requests to the camera driver.



## -syntax

````
typedef struct {
  ULONG VideoStabilizationMode;
  ULONG Capabilities;
} KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S, *PKSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S;
````


## -struct-fields

### -field VideoStabilizationMode

Indicates the selected video stabilization modes. This member has one of these possible values:


### -field KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_OFF

<dd>
The video stabilization mode should not activate.


### -field KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_AUTO

<dd>
The device automatically controls video stabilization.  This value is valid only if <b>KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_FLAGS_AUTO</b> is set in the <b>Capabilities</b> member.


### -field KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_LOW

<dd>
Video stabilization is set at a low level.


### -field KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_MEDIUM

<dd>
Video stabilization is set at a medium level.


### -field KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_HIGH

<dd>
Video stabilization is set at a high level.

</dd>
</dl>

### -field Capabilities

Indicates whether the device and driver support setting video stabilization control automatically or manually. This member a bitwise <b>OR</b> of these possible values:


### -field KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_FLAGS_AUTO

<dd>
The device and driver can automatically control video stabilization.


### -field KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_FLAGS_MANUAL

<dd>
The user can manually set video stabilization modes.

</dd>
</dl>

## -remarks
The video stabilization settings specified with this structure affect only the device and have no effect on applications' software video stabilization.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
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
<a href="..\ksmedia\ne-ksmedia-ksproperty_cameracontrol_video_stabilization_mode.md">KSPROPERTY_CAMERACONTROL_VIDEO_STABILIZATION_MODE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj156043">KSPROPERTY_CAMERACONTROL_VIDEO_STABILIZATION_MODE_PROPERTY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

