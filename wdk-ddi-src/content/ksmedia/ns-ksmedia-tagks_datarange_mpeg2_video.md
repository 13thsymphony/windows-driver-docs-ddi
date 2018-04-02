---
UID: NS:ksmedia.tagKS_DATARANGE_MPEG2_VIDEO
title: tagKS_DATARANGE_MPEG2_VIDEO
author: windows-driver-content
description: The KS_DATARANGE_MPEG2_VIDEO structure describes the range of MPEG-2 video formats available for a stream.
old-location: stream\ks_datarange_mpeg2_video.htm
old-project: stream
ms.assetid: ed29c80a-7a42-46e3-8a18-d66dfddb9659
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKS_DATARANGE_MPEG2_VIDEO, KS_DATARANGE_MPEG2_VIDEO, KS_DATARANGE_MPEG2_VIDEO structure [Streaming Media Devices], PKS_DATARANGE_MPEG2_VIDEO, PKS_DATARANGE_MPEG2_VIDEO structure pointer [Streaming Media Devices], ksmedia/KS_DATARANGE_MPEG2_VIDEO, ksmedia/PKS_DATARANGE_MPEG2_VIDEO, stream.ks_datarange_mpeg2_video, tagKS_DATARANGE_MPEG2_VIDEO, vidcapstruct_91d79090-6aa2-4037-8436-7cb21d242e72.xml"
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
-	ksmedia.h
api_name:
-	KS_DATARANGE_MPEG2_VIDEO
product:
- Windows
targetos: Windows
req.typenames: KS_DATARANGE_MPEG2_VIDEO, *PKS_DATARANGE_MPEG2_VIDEO
---

# tagKS_DATARANGE_MPEG2_VIDEO structure
The KS_DATARANGE_MPEG2_VIDEO structure describes the range of MPEG-2 video formats available for a stream.

## Syntax
```
typedef struct tagKS_DATARANGE_MPEG2_VIDEO {
  KSDATARANGE                 DataRange;
  BOOL                        bFixedSizeSamples;
  BOOL                        bTemporalCompression;
  DWORD                       StreamDescriptionFlags;
  DWORD                       MemoryAllocationFlags;
  KS_VIDEO_STREAM_CONFIG_CAPS ConfigCaps;
  KS_MPEGVIDEOINFO2           VideoInfoHeader;
} *PKS_DATARANGE_MPEG2_VIDEO, KS_DATARANGE_MPEG2_VIDEO;
```

## Members


`DataRange`

Specifies the major identifier for the format.

`bFixedSizeSamples`

Specifies that all the samples are the same size if set to <b>TRUE</b>.

`bTemporalCompression`

Specifies whether each sample can stand independently on its own, without relying on previous or future samples.

`StreamDescriptionFlags`

Unused and should be set to zero.

`MemoryAllocationFlags`

Unused and should be set to zero.

`ConfigCaps`

Specifies the configuration of the stream, including scaling, cropping, and frame and data rates.

`VideoInfoHeader`

Specifies the details of the video stream.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567667">KS_MPEGVIDEOINFO2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567706">KS_VIDEO_STREAM_CONFIG_CAPS</a>