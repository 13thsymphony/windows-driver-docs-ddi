---
UID : NS:ksmedia._KSCAMERA_PROFILE_MEDIAINFO
title : "_KSCAMERA_PROFILE_MEDIAINFO"
author : windows-driver-content
description : This structure contains the relevant media type information presented for each camera profile.
old-location : stream\kscamera_profile_mediainfo.htm
old-project : stream
ms.assetid : 55B9F032-A3F5-434E-9EB6-CB832DC0EB45
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : PKSCAMERA_PROFILE_MEDIAINFO, ksmedia/PKSCAMERA_PROFILE_MEDIAINFO, PKSCAMERA_PROFILE_MEDIAINFO structure pointer [Streaming Media Devices], KSCAMERA_PROFILE_MEDIAINFO, KSCAMERA_PROFILE_MEDIAINFO structure [Streaming Media Devices], stream.kscamera_profile_mediainfo, ksmedia/KSCAMERA_PROFILE_MEDIAINFO, _KSCAMERA_PROFILE_MEDIAINFO, *PKSCAMERA_PROFILE_MEDIAINFO
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
req.typenames : KSCAMERA_PROFILE_MEDIAINFO, *PKSCAMERA_PROFILE_MEDIAINFO
---

# _KSCAMERA_PROFILE_MEDIAINFO structure
This structure contains the relevant media type information presented for each camera profile.

## Syntax
````
typedef struct _KSCAMERA_PROFILE_MEDIAINFO {
  struct {
    UINT32 X;
    UINT32 Y;
  } Resolution;
  struct {
    UINT32 Numerator;
    UINT32 Denominator;
  } MaxFrameRate;
  ULONGLONG Flags;
  UINT32    Data0;
  UINT32    Data1;
  UINT32    Data2;
  UINT32    Data3;
} KSCAMERA_PROFILE_MEDIAINFO, *PKSCAMERA_PROFILE_MEDIAINFO;
````

## Members


`Data0`

Reserved. Must be set to 0.

`Data1`

Reserved. Must be set to 0.

`Data2`

Reserved. Must be set to 0.

`Data3`

Reserved. Must be set to 0.

`Flags`

The  bitwise OR of one or more of the following flags:
<ul>
<li>KSCAMERAPROFILE_FLAGS_VIDEOHDRWhen the video HDR flag is set for the media info, for that media setting, video HDR may be enabled for the record stream.

This flag may not be set for media info on the photo pin.

</li>
<li>KSCAMERAPROFILE_FLAGS_VARIABLEPHOTOSEQUENCEWhen the Variable Photo Sequence flag is set for the media info, VPS support is available even if the photo media info does not provide a frame rate.

If this flag is set and the frame rate is non-zero, for that photo media info, VPS and Photo Sequence is available.

If this flag is set and the frame rate is zero, for that photo media info, VPS is available but not Photo Sequence.

If this flag is not set and the  frame rate is non-zero, for that photo media info, VPS is not available but Photo Sequence is available.

If  this flag is not set and the frame rate is zero, neither VPS nor Photo Sequence is available for that media info.

This flag may only be set for media info on the photo pin.  Presence of this flag on non-photo pin media info will result in the profile set being rejected.

</li>
</ul>

`MaxFrameRate`

The numerator/denominator ratio of frame rate (for example, 30 / 1 = 30fps).  This frame rate represents the maximum frame rate of the specified resolution under ideal lighting conditions.  Actual frame rate may be lower than this value.

For photo media information, if photo sequence cannot be enabled because of hardware constraints for the given photo resolution, the frame rate must be set to 0 (numerator=0, denominator=0).  This will inform the application layer that photo sequence control will be rejected by the driver when that particular photo media type is selected.

`Resolution`

The X (horizontal) and Y (vertical) frame size in pixels.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h |