---
UID : NS:ksmedia._KSCAMERA_PROFILE_CONCURRENCYINFO
title : "_KSCAMERA_PROFILE_CONCURRENCYINFO"
author : windows-driver-content
description : An array of KSCAMERA_PROFILE_CONCURRENCYINFO structures form the Camera.Concurrency parameter of the KSDEVICE_PROFILE_INFO structure (whose array size is specified by Camera.CountOfConcurrency parameter) indicating which profiles the profile identified in the KSCAMERA_PROFILE_INFO structure may run simultaneously on different cameras.
old-location : stream\kscamera_profile_concurrencyinfo.htm
old-project : stream
ms.assetid : 4E0A9CE6-2FA0-46A5-B478-C088E5FF1BAD
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ksmedia/KSCAMERA_PROFILE_CONCURRENCYINFO, KSCAMERA_PROFILE_CONCURRENCYINFO, KSCAMERA_PROFILE_CONCURRENCYINFO structure [Streaming Media Devices], PKSCAMERA_PROFILE_CONCURRENCYINFO structure pointer [Streaming Media Devices], _KSCAMERA_PROFILE_CONCURRENCYINFO, *PKSCAMERA_PROFILE_CONCURRENCYINFO, ksmedia/PKSCAMERA_PROFILE_CONCURRENCYINFO, PKSCAMERA_PROFILE_CONCURRENCYINFO, stream.kscamera_profile_concurrencyinfo
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ksmedia.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : KSCAMERA_PROFILE_CONCURRENCYINFO, *PKSCAMERA_PROFILE_CONCURRENCYINFO
---

# _KSCAMERA_PROFILE_CONCURRENCYINFO structure
An array of <b>KSCAMERA_PROFILE_CONCURRENCYINFO</b> structures form the <b>Camera.Concurrency</b> parameter of   the <a href="..\ksmedia\ns-ksmedia-_ksdevice_profile_info.md">KSDEVICE_PROFILE_INFO</a> structure (whose array size is specified by <b>Camera.CountOfConcurrency</b> parameter) indicating which profiles the profile identified in the <a href="..\ksmedia\ns-ksmedia-_kscamera_profile_info.md">KSCAMERA_PROFILE_INFO</a> structure may run simultaneously on different cameras.

## Syntax
````
typedef struct _KSCAMERA_PROFILE_CONCURRENCYINFO {
  GUID                      ReferenceGuid;
  UINT32                    Reserved;
  UINT32                    ProfileCount;
  PKSCAMERA_PROFILE_PININFO Profiles;
} KSCAMERA_PROFILE_CONCURRENCYINFO, *PKSCAMERA_PROFILE_CONCURRENCYINFO;
````

## Members


`ProfileCount`

Number of profile IDs contained in the <b>Profiles</b> array.  Must be greater than 0.

`Profiles`

This is an array of <b>KSCAMERA_PROFILE_INFO</b> structures that can be simultaneously used on the other camera device specified by the <b>ReferenceGuid</b>. This field must not be <b>NULL</b>.

`ReferenceGuid`

Must be set to the <b>ReferenceGuid</b> of the <b>KSFILTER_DESCRIPTOR</b> which corresponds to the other device with which this profile is concurrent.

`Reserved`

Unused.  Must be 0.

## Remarks
Currently, an application has no knowledge as to whether it can attempt to stream from more than one camera until the attempt succeeds or fails.  In the case of web blogging scenario, this means the application will have to attempt to activate both streams before it paints the UI with a picture in picture video element.

For multiple applications, concurrency will not be sufficient to guarantee concurrent operation.  The concurrency information will not attempt to solve this scenario.  Instead, the existing camera yanking feature will be leveraged.

If both <b>Camera.CountOfConcurrency</b> and the <b>Camera.Concurrency</b> fields are 0 and <b>NULL</b> respectively, it indicates to the OS that the profile defined by the KSCAMERA_PROFILE_INFO is not a concurrent profile.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h |