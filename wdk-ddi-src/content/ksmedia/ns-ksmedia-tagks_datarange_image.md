---
UID: NS:ksmedia.tagKS_DATARANGE_IMAGE
title: tagKS_DATARANGE_IMAGE
author: windows-driver-content
description: Specifies an image data range that is used in the KSPIN_DESCRIPTOR structure that describes a pin (or stream).
old-location: stream\ks_datarange_image.htm
old-project: stream
ms.assetid: 81ad341a-5f68-43aa-98ea-193780a7c5b2
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksmedia/PKS_DATARANGE_IMAGE, ksmedia/KS_DATARANGE_IMAGE, stream.ks_datarange_image, tagKS_DATARANGE_IMAGE, PKS_DATARANGE_IMAGE, *PKS_DATARANGE_IMAGE, KS_DATARANGE_IMAGE structure [Streaming Media Devices], KS_DATARANGE_IMAGE, PKS_DATARANGE_IMAGE structure pointer [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	Ksmedia.h
apiname:
-	KS_DATARANGE_IMAGE
product: Windows
targetos: Windows
req.typenames: KS_DATARANGE_IMAGE, *PKS_DATARANGE_IMAGE
---

# tagKS_DATARANGE_IMAGE structure
Specifies an image data range that is used in the <a href="..\ks\ns-ks-kspin_descriptor.md">KSPIN_DESCRIPTOR</a> structure that describes a pin (or stream).

## Syntax
````
typedef struct tagKS_DATARANGE_IMAGE {
  KSDATARANGE                 DataRange;
  KS_VIDEO_STREAM_CONFIG_CAPS ConfigCaps;
  KS_BITMAPINFOHEADER         ImageInfoHeader;
} KS_DATARANGE_IMAGE, *PKS_DATARANGE_IMAGE;
````

## Members


`ConfigCaps`

A <a href="..\ksmedia\ns-ksmedia-_ks_video_stream_config_caps.md">KS_VIDEO_STREAM_CONFIG_CAPS</a> structure that specifies the configuration of the stream, including scaling, cropping, and frame and data rates.

`DataRange`

A <a href="..\ks\ns-ks-ksdataformat.md">KSDATARANGE</a> structure that specifies the data range supported by this pin type.

`ImageInfoHeader`

A <a href="..\ksmedia\ns-ksmedia-tagks_bitmapinfoheader.md">KS_BITMAPINFOHEADER</a> structure that specifies image color and dimension information that the still image capture stream would provide.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="..\ksmedia\ns-ksmedia-_ks_video_stream_config_caps.md">KS_VIDEO_STREAM_CONFIG_CAPS</a>

<a href="..\ks\ns-ks-kspin_descriptor.md">KSPIN_DESCRIPTOR</a>

<a href="..\ks\ns-ks-ksdataformat.md">KSDATARANGE</a>

<a href="..\ksmedia\ns-ksmedia-tagks_bitmapinfoheader.md">KS_BITMAPINFOHEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DATARANGE_IMAGE structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>