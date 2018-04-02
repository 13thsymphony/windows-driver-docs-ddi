---
UID: NS:ksmedia.tagKS_MPEG1VIDEOINFO
title: tagKS_MPEG1VIDEOINFO
author: windows-driver-content
description: The KS_MPEG1VIDEOINFO structure describes an MPEG-1 video stream.
old-location: stream\ks_mpeg1videoinfo.htm
old-project: stream
ms.assetid: 301b954a-4e50-4a04-a575-17d7d54fa691
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKS_MPEG1VIDEOINFO, KS_MPEG1VIDEOINFO, KS_MPEG1VIDEOINFO structure [Streaming Media Devices], PKS_MPEG1VIDEOINFO, PKS_MPEG1VIDEOINFO structure pointer [Streaming Media Devices], ksmedia/KS_MPEG1VIDEOINFO, ksmedia/PKS_MPEG1VIDEOINFO, stream.ks_mpeg1videoinfo, tagKS_MPEG1VIDEOINFO, vidcapstruct_5c9e7f76-f279-49fb-9ad8-f23b7741d685.xml"
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
-	KS_MPEG1VIDEOINFO
product:
- Windows
targetos: Windows
req.typenames: KS_MPEG1VIDEOINFO, *PKS_MPEG1VIDEOINFO
---

# tagKS_MPEG1VIDEOINFO structure
The KS_MPEG1VIDEOINFO structure describes an MPEG-1 video stream.

## Syntax
```
typedef struct tagKS_MPEG1VIDEOINFO {
  KS_VIDEOINFOHEADER hdr;
  DWORD              dwStartTimeCode;
  DWORD              cbSequenceHeader;
  BYTE               bSequenceHeader[1];
} *PKS_MPEG1VIDEOINFO, KS_MPEG1VIDEOINFO;
```

## Members


`hdr`

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567700">KS_VIDEOINFOHEADER</a> structure that describes the details of the video stream.

`dwStartTimeCode`

A 25-bit "group-of-pictures" time code at the start of data.

`cbSequenceHeader`

The length of the <b>bSequenceHeader</b> member, in bytes.

`bSequenceHeader`

The length of the <b>bSequenceHeader</b> member, in bytes.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567700">KS_VIDEOINFOHEADER</a>