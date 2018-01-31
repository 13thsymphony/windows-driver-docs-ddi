---
UID : NS:ksmedia.tagKS_DATARANGE_MPEG2_VIDEO
title : tagKS_DATARANGE_MPEG2_VIDEO
author : windows-driver-content
description : The KS_DATARANGE_MPEG2_VIDEO structure describes the range of MPEG-2 video formats available for a stream.
old-location : stream\ks_datarange_mpeg2_video.htm
old-project : stream
ms.assetid : ed29c80a-7a42-46e3-8a18-d66dfddb9659
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ksmedia/KS_DATARANGE_MPEG2_VIDEO, vidcapstruct_91d79090-6aa2-4037-8436-7cb21d242e72.xml, *PKS_DATARANGE_MPEG2_VIDEO, KS_DATARANGE_MPEG2_VIDEO, PKS_DATARANGE_MPEG2_VIDEO, tagKS_DATARANGE_MPEG2_VIDEO, PKS_DATARANGE_MPEG2_VIDEO structure pointer [Streaming Media Devices], stream.ks_datarange_mpeg2_video, ksmedia/PKS_DATARANGE_MPEG2_VIDEO, KS_DATARANGE_MPEG2_VIDEO structure [Streaming Media Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ksmedia.h
req.include-header : Ksmedia.h
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
req.typenames : KS_DATARANGE_MPEG2_VIDEO, *PKS_DATARANGE_MPEG2_VIDEO
---

# tagKS_DATARANGE_MPEG2_VIDEO structure
The KS_DATARANGE_MPEG2_VIDEO structure describes the range of MPEG-2 video formats available for a stream.

## Syntax
````
typedef struct tagKS_DATARANGE_MPEG2_VIDEO {
  KSDATARANGE                 DataRange;
  BOOL                        bFixedSizeSamples;
  BOOL                        bTemporalCompression;
  DWORD                       StreamDescriptionFlags;
  DWORD                       MemoryAllocationFlags;
  KS_VIDEO_STREAM_CONFIG_CAPS ConfigCaps;
  KS_MPEGVIDEOINFO2           VideoInfoHeader;
} KS_DATARANGE_MPEG2_VIDEO, *PKS_DATARANGE_MPEG2_VIDEO;
````

## Members


`bFixedSizeSamples`

Specifies that all the samples are the same size if set to <b>TRUE</b>.

`bTemporalCompression`

Specifies whether each sample can stand independently on its own, without relying on previous or future samples.

`ConfigCaps`

Specifies the configuration of the stream, including scaling, cropping, and frame and data rates.

`DataRange`

Specifies the major identifier for the format.

`MemoryAllocationFlags`

Unused and should be set to zero.

`StreamDescriptionFlags`

Unused and should be set to zero.

`VideoInfoHeader`

Specifies the details of the video stream.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="..\ksmedia\ns-ksmedia-tagks_mpegvideoinfo2.md">KS_MPEGVIDEOINFO2</a>

<a href="..\ksmedia\ns-ksmedia-_ks_video_stream_config_caps.md">KS_VIDEO_STREAM_CONFIG_CAPS</a>

<a href="..\ks\ns-ks-ksdataformat.md">KSDATARANGE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DATARANGE_MPEG2_VIDEO structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>