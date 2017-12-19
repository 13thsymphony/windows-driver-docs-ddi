---
UID: NS.KSMEDIA._KSCAMERA_EXTENDEDPROP_PROFILE
title: _KSCAMERA_EXTENDEDPROP_PROFILE
author: windows-driver-content
description: The payload of the KSPROPERTY_CAMERACONTROL_EXTENDED_PROFILE control contains KSCAMERA_EXTENDEDPROP_HEADER + KSCAMERA_EXTENDEDPROP_PROFILE.
old-location: stream\kscamera_extendedprop_profile.htm
old-project: stream
ms.assetid: 43529BA7-1F5A-4B9B-9792-2D6050F0480D
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _KSCAMERA_EXTENDEDPROP_PROFILE, *PKSCAMERA_EXTENDEDPROP_PROFILE, KSCAMERA_EXTENDEDPROP_PROFILE, PKSCAMERA_EXTENDEDPROP_PROFILE
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
req.alt-api: KSCAMERA_EXTENDEDPROP_PROFILE
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

# _KSCAMERA_EXTENDEDPROP_PROFILE structure



## -description
The payload of the KSPROPERTY_CAMERACONTROL_EXTENDED_PROFILE control contains KSCAMERA_EXTENDEDPROP_HEADER + KSCAMERA_EXTENDEDPROP_PROFILE.



## -syntax

````
typedef struct _KSCAMERA_EXTENDEDPROP_PROFILE {
  GUID   ProfileId;
  UINT32 Index;
  UINT32 Reserved;
} KSCAMERA_EXTENDEDPROP_PROFILE, *PKSCAMERA_EXTENDEDPROP_PROFILE;
````


## -struct-fields

### -field ProfileId

A GUID representing the selected profile.  If this is KSCAMERAPROFILE_Legacy, no profile was selected, the camera driver must expose the Reduced Set Media Type.

If this field is GUID_NULL, no profile was selected, but the application is profile aware so the camera driver must expose the full range of media types.


### -field Index

An index value associated with the identified profile.


### -field Reserved

Unused.  Must be 0.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ksmedia.h</dt>
</dl>
</td>
</tr>
</table>