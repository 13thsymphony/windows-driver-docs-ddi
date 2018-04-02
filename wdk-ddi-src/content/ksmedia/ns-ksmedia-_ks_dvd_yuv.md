---
UID: NS:ksmedia._KS_DVD_YUV
title: "_KS_DVD_YUV"
author: windows-driver-content
description: The KS_DVD_YUV structure is used to describe a color in the YUV colorspace.
old-location: stream\ks_dvd_yuv.htm
old-project: stream
ms.assetid: 9b155d09-6fb2-4c6c-bde6-7eadeb09bc40
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKS_DVD_YUV, KS_DVD_YUV, KS_DVD_YUV structure [Streaming Media Devices], PKS_DVD_YUV, PKS_DVD_YUV structure pointer [Streaming Media Devices], _KS_DVD_YUV, dvdref_ea41e501-8a59-4d54-8dde-792ce2673b8c.xml, ksmedia/KS_DVD_YUV, ksmedia/PKS_DVD_YUV, stream.ks_dvd_yuv"
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
-	KS_DVD_YUV
product: Windows
targetos: Windows
req.typenames: KS_DVD_YUV, *PKS_DVD_YUV
---

# _KS_DVD_YUV structure
The KS_DVD_YUV structure is used to describe a color in the YUV colorspace.

## Syntax
```
typedef struct _KS_DVD_YUV {
  UCHAR Reserved;
  UCHAR Y;
  UCHAR V;
  UCHAR U;
} *PKS_DVD_YUV, KS_DVD_YUV;
```

## Members


`Reserved`

Reserved. Do not use.

`Y`

Indicates the luminance (brightness) component of the color.

`V`

Indicates the color-red (chrominance) component of the color.

`U`

Indicates the color-blue (chrominance) component of the color.

## Remarks
The KS_DVD_YUV structure is used

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567641">KS_DVD_YCrCb</a>