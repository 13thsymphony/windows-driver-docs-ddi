---
UID: NS:ksmedia.tagKS_VBIINFOHEADER
title: tagKS_VBIINFOHEADER
author: windows-driver-content
description: The KS_VBIINFOHEADER structure describes raw vertical blanking interval (VBI) streams.
old-location: stream\ks_vbiinfoheader.htm
old-project: stream
ms.assetid: 4424be3a-6e73-449c-b5fb-5cbc1109490d
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PKS_VBIINFOHEADER, tagKS_VBIINFOHEADER, KS_VBIINFOHEADER, vidcapstruct_2a637c59-2852-4b59-9d92-f51c9892df85.xml, ksmedia/KS_VBIINFOHEADER, stream.ks_vbiinfoheader, KS_VBIINFOHEADER structure [Streaming Media Devices], ksmedia/PKS_VBIINFOHEADER, *PKS_VBIINFOHEADER, PKS_VBIINFOHEADER structure pointer [Streaming Media Devices]
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
-	KS_VBIINFOHEADER
product: Windows
targetos: Windows
req.typenames: KS_VBIINFOHEADER, *PKS_VBIINFOHEADER
---

# tagKS_VBIINFOHEADER structure
The KS_VBIINFOHEADER structure describes raw vertical blanking interval (VBI) streams.

## Syntax
````
typedef struct tagKS_VBIINFOHEADER {
  ULONG StartLine;
  ULONG EndLine;
  ULONG SamplingFrequency;
  ULONG MinLineStartTime;
  ULONG MaxLineStartTime;
  ULONG ActualLineStartTime;
  ULONG ActualLineEndTime;
  ULONG VideoStandard;
  ULONG SamplesPerLine;
  ULONG StrideInBytes;
  ULONG BufferSize;
} KS_VBIINFOHEADER, *PKS_VBIINFOHEADER;
````

## Members


`ActualLineEndTime`

Specifies the actual ending point for VBI digitization from the leading edge of H-sync in 10-nanosecond units (that is, in hundredths of microseconds).

`ActualLineStartTime`

Specifies the actual starting point of VBI digitization from the leading edge of H-sync in 10-nanosecond units (that is, in hundredths of microseconds).

`BufferSize`

Specifies the size in bytes of the buffer to store the entire digitized VBI signal.

`EndLine`

Specifies the line number of the last digitized VBI line.

`MaxLineStartTime`

Specifies the longest possible interval from the leading edge of H-sync in 10-nanosecond units (that is, in hundredths of microseconds).

`MinLineStartTime`

Specifies the shortest possible interval from the leading edge of H-sync in 10-nanosecond units (that is, in hundredths of microseconds).

`SamplesPerLine`

Specifies the number of samples digitized per video line.

`SamplingFrequency`

Specifies the sampling frequency in hertz (Hz).

`StartLine`

Specifies the line number of the first digitized VBI line.

`StrideInBytes`

Specifies the stride in bytes between the first sample on a given line and the first sample on the next line. This value can be larger than <b>SamplesPerLine</b>.

`VideoStandard`

Specifies one or more (logically ORed) values from the <a href="..\ksmedia\ne-ksmedia-ks_analogvideostandard.md">KS_AnalogVideoStandard</a> enumeration.

## Remarks
VBI streams are usually converted to NABTS, CC, and WST streams by downstream filters.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="..\ksmedia\ne-ksmedia-ks_analogvideostandard.md">KS_AnalogVideoStandard</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_VBIINFOHEADER structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>