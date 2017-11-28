---
UID: NS.ksmedia._KSCAMERA_PROFILE_CONCURRENCYINFO
title: KSCAMERA_PROFILE_CONCURRENCYINFO
author: windows-driver-content
description: An array of KSCAMERA_PROFILE_CONCURRENCYINFO structures form the Camera.Concurrency parameter of the KSDEVICE_PROFILE_INFO structure (whose array size is specified by Camera.CountOfConcurrency parameter) indicating which profiles the profile identified in the KSCAMERA_PROFILE_INFO structure may run simultaneously on different cameras.
old-location: stream\kscamera_profile_concurrencyinfo.htm
old-project: stream
ms.assetid: 4E0A9CE6-2FA0-46A5-B478-C088E5FF1BAD
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: KSCAMERA_PROFILE_CONCURRENCYINFO, KSCAMERA_PROFILE_CONCURRENCYINFO, *PKSCAMERA_PROFILE_CONCURRENCYINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSCAMERA_PROFILE_CONCURRENCYINFO
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

# KSCAMERA_PROFILE_CONCURRENCYINFO structure



## -description
<p>An array of <b>KSCAMERA_PROFILE_CONCURRENCYINFO</b> structures form the <b>Camera.Concurrency</b> parameter of   the <a href="https://msdn.microsoft.com/library/windows/hardware/dn925223">KSDEVICE_PROFILE_INFO</a> structure (whose array size is specified by <b>Camera.CountOfConcurrency</b> parameter) indicating which profiles the profile identified in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn925214">KSCAMERA_PROFILE_INFO</a> structure may run simultaneously on different cameras.</p>


## -syntax

````
typedef struct _KSCAMERA_PROFILE_CONCURRENCYINFO {
  GUID                      ReferenceGuid;
  UINT32                    Reserved;
  UINT32                    ProfileCount;
  PKSCAMERA_PROFILE_PININFO Profiles;
} KSCAMERA_PROFILE_CONCURRENCYINFO, *PKSCAMERA_PROFILE_CONCURRENCYINFO;
````


## -struct-fields
<dl>

### -field <b>ReferenceGuid</b>

<dd>
<p>Must be set to the <b>ReferenceGuid</b> of the <b>KSFILTER_DESCRIPTOR</b> which corresponds to the other device with which this profile is concurrent.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>Unused.  Must be 0.</p>
</dd>

### -field <b>ProfileCount</b>

<dd>
<p>Number of profile IDs contained in the <b>Profiles</b> array.  Must be greater than 0.</p>
</dd>

### -field <b>Profiles</b>

<dd>
<p>This is an array of <b>KSCAMERA_PROFILE_INFO</b> structures that can be simultaneously used on the other camera device specified by the <b>ReferenceGuid</b>. This field must not be <b>NULL</b>.</p>
</dd>
</dl>

## -remarks
<p>Currently, an application has no knowledge as to whether it can attempt to stream from more than one camera until the attempt succeeds or fails.  In the case of web blogging scenario, this means the application will have to attempt to activate both streams before it paints the UI with a picture in picture video element.</p>

<p>For multiple applications, concurrency will not be sufficient to guarantee concurrent operation.  The concurrency information will not attempt to solve this scenario.  Instead, the existing camera yanking feature will be leveraged.</p>

<p>If both <b>Camera.CountOfConcurrency</b> and the <b>Camera.Concurrency</b> fields are 0 and <b>NULL</b> respectively, it indicates to the OS that the profile defined by the KSCAMERA_PROFILE_INFO is not a concurrent profile.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ksmedia.h</dt>
</dl>
</td>
</tr>
</table>