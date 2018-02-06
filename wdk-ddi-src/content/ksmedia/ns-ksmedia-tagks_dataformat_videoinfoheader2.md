---
UID: NS:ksmedia.tagKS_DATAFORMAT_VIDEOINFOHEADER2
title: tagKS_DATAFORMAT_VIDEOINFOHEADER2
author: windows-driver-content
description: The KS_DATAFORMAT_VIDEOINFOHEADER2 structure describes a video stream that includes settings for bob or weave.
old-location: stream\ks_dataformat_videoinfoheader2.htm
old-project: stream
ms.assetid: 92deaecd-69d7-4e64-bdb0-a2736add0c2f
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KS_DATAFORMAT_VIDEOINFOHEADER2, stream.ks_dataformat_videoinfoheader2, PKS_DATAFORMAT_VIDEOINFOHEADER2 structure pointer [Streaming Media Devices], ksmedia/KS_DATAFORMAT_VIDEOINFOHEADER2, *PKS_DATAFORMAT_VIDEOINFOHEADER2, PKS_DATAFORMAT_VIDEOINFOHEADER2, ksmedia/PKS_DATAFORMAT_VIDEOINFOHEADER2, KS_DATAFORMAT_VIDEOINFOHEADER2 structure [Streaming Media Devices], vidcapstruct_cadaf63f-50d5-41c5-926b-81724dddb890.xml, tagKS_DATAFORMAT_VIDEOINFOHEADER2
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
-	KS_DATAFORMAT_VIDEOINFOHEADER2
product: Windows
targetos: Windows
req.typenames: "*PKS_DATAFORMAT_VIDEOINFOHEADER2, KS_DATAFORMAT_VIDEOINFOHEADER2"
---

# tagKS_DATAFORMAT_VIDEOINFOHEADER2 structure
The KS_DATAFORMAT_VIDEOINFOHEADER2 structure describes a video stream that includes settings for bob or weave.

## Syntax
````
typedef struct tagKS_DATAFORMAT_VIDEOINFOHEADER2 {
  KSDATAFORMAT        DataFormat;
  KS_VIDEOINFOHEADER2 VideoInfoHeader2;
} KS_DATAFORMAT_VIDEOINFOHEADER2, *PKS_DATAFORMAT_VIDEOINFOHEADER2;
````

## Members


`DataFormat`

Specifies the data format.

`VideoInfoHeader2`

Specifies the details of the video stream, including options for specifying bob or weave settings.

## Remarks
Minidrivers that do not need to specify bob or weave settings may use the <a href="..\ksmedia\ns-ksmedia-tagks_dataformat_videoinfoheader.md">KS_DATAFORMAT_VIDEOINFOHEADER</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="..\ksmedia\ns-ksmedia-tagks_videoinfoheader2.md">KS_VIDEOINFOHEADER2</a>

<a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a>

<a href="..\ksmedia\ns-ksmedia-tagks_videoinfoheader.md">KS_VIDEOINFOHEADER</a>

<a href="..\ksmedia\ns-ksmedia-tagks_dataformat_videoinfoheader.md">KS_DATAFORMAT_VIDEOINFOHEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DATAFORMAT_VIDEOINFOHEADER2 structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>