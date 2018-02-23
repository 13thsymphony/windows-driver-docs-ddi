---
UID: NS:ksmedia.tagKS_DATARANGE_VIDEO2
title: tagKS_DATARANGE_VIDEO2
author: windows-driver-content
description: The KS_DATARANGE_VIDEO2 structure describes a video stream including bob or weave settings.
old-location: stream\ks_datarange_video2.htm
old-project: stream
ms.assetid: bddb19cb-7705-470b-ad22-14fd72f3db11
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: PKS_DATARANGE_VIDEO2, ksmedia/PKS_DATARANGE_VIDEO2, vidcapstruct_f014ea98-b1a5-4d05-aea3-b13e7a3f5918.xml, tagKS_DATARANGE_VIDEO2, ksmedia/KS_DATARANGE_VIDEO2, *PKS_DATARANGE_VIDEO2, KS_DATARANGE_VIDEO2, stream.ks_datarange_video2, KS_DATARANGE_VIDEO2 structure [Streaming Media Devices], PKS_DATARANGE_VIDEO2 structure pointer [Streaming Media Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KS_DATARANGE_VIDEO2
product: Windows
targetos: Windows
req.typenames: KS_DATARANGE_VIDEO2, *PKS_DATARANGE_VIDEO2
---

# tagKS_DATARANGE_VIDEO2 structure
The KS_DATARANGE_VIDEO2 structure describes a video stream including bob or weave settings.

## Syntax
````
typedef struct tagKS_DATARANGE_VIDEO2 {
  KSDATARANGE                 DataRange;
  BOOL                        bFixedSizeSamples;
  BOOL                        bTemporalCompression;
  DWORD                       StreamDescriptionFlags;
  DWORD                       MemoryAllocationFlags;
  KS_VIDEO_STREAM_CONFIG_CAPS ConfigCaps;
  KS_VIDEOINFOHEADER2         VideoInfoHeader;
} KS_DATARANGE_VIDEO2, *PKS_DATARANGE_VIDEO2;
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

## Remarks
This structure should be used instead of a <a href="..\ksmedia\ns-ksmedia-tagks_datarange_video.md">KS_DATARANGE_VIDEO</a> structure when a minidriver must describe content with bob or weave settings.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="..\ks\ns-ks-ksdataformat.md">KSDATARANGE</a>



<a href="..\ksmedia\ns-ksmedia-_ks_video_stream_config_caps.md">KS_VIDEO_STREAM_CONFIG_CAPS</a>



<a href="..\ksmedia\ns-ksmedia-tagks_videoinfoheader2.md">KS_VIDEOINFOHEADER2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DATARANGE_VIDEO2 structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>