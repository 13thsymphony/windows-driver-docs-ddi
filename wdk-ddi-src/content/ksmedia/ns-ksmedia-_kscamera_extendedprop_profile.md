---
UID: NS:ksmedia._KSCAMERA_EXTENDEDPROP_PROFILE
title: "_KSCAMERA_EXTENDEDPROP_PROFILE"
author: windows-driver-content
description: The payload of the KSPROPERTY_CAMERACONTROL_EXTENDED_PROFILE control contains KSCAMERA_EXTENDEDPROP_HEADER + KSCAMERA_EXTENDEDPROP_PROFILE.
old-location: stream\kscamera_extendedprop_profile.htm
old-project: stream
ms.assetid: 43529BA7-1F5A-4B9B-9792-2D6050F0480D
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSCAMERA_EXTENDEDPROP_PROFILE, KSCAMERA_EXTENDEDPROP_PROFILE, KSCAMERA_EXTENDEDPROP_PROFILE structure [Streaming Media Devices], PKSCAMERA_EXTENDEDPROP_PROFILE, PKSCAMERA_EXTENDEDPROP_PROFILE structure pointer [Streaming Media Devices], _KSCAMERA_EXTENDEDPROP_PROFILE, ksmedia/KSCAMERA_EXTENDEDPROP_PROFILE, ksmedia/PKSCAMERA_EXTENDEDPROP_PROFILE, stream.kscamera_extendedprop_profile"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ksmedia.h
api_name:
-	KSCAMERA_EXTENDEDPROP_PROFILE
product:
- Windows
targetos: Windows
req.typenames: KSCAMERA_EXTENDEDPROP_PROFILE, *PKSCAMERA_EXTENDEDPROP_PROFILE
---

# _KSCAMERA_EXTENDEDPROP_PROFILE structure
The payload of the KSPROPERTY_CAMERACONTROL_EXTENDED_PROFILE control contains KSCAMERA_EXTENDEDPROP_HEADER + KSCAMERA_EXTENDEDPROP_PROFILE.

## Syntax
```
typedef struct _KSCAMERA_EXTENDEDPROP_PROFILE {
  GUID   ProfileId;
  UINT32 Index;
  UINT32 Reserved;
} KSCAMERA_EXTENDEDPROP_PROFILE, *PKSCAMERA_EXTENDEDPROP_PROFILE;
```

## Members


`ProfileId`

A GUID representing the selected profile.  If this is KSCAMERAPROFILE_Legacy, no profile was selected, the camera driver must expose the Reduced Set Media Type.

If this field is GUID_NULL, no profile was selected, but the application is profile aware so the camera driver must expose the full range of media types.

`Index`

An index value associated with the identified profile.

`Reserved`

Unused.  Must be 0.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h |