---
UID: NS:ksmedia._KS_DVD_YCrCb
title: "_KS_DVD_YCrCb"
author: windows-driver-content
description: The KS_DVD_YCrCb structure is used to describe a color in the YCrCb colorspace.
old-location: stream\ks_dvd_ycrcb.htm
old-project: stream
ms.assetid: 78010e49-ad09-4eb3-bb48-17040737a0a0
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKS_DVD_YCrCb, KS_DVD_YCrCb, KS_DVD_YCrCb structure [Streaming Media Devices], PKS_DVD_YCrCb, PKS_DVD_YCrCb structure pointer [Streaming Media Devices], _KS_DVD_YCrCb, dvdref_559830d7-6f86-4a27-bc31-1e0e7928d7d4.xml, ksmedia/KS_DVD_YCrCb, ksmedia/PKS_DVD_YCrCb, stream.ks_dvd_ycrcb"
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
-	KS_DVD_YCrCb
product: Windows
targetos: Windows
req.typenames: KS_DVD_YCrCb, *PKS_DVD_YCrCb
---

# _KS_DVD_YCrCb structure
The KS_DVD_YCrCb structure is used to describe a color in the YCrCb colorspace.

## Syntax
````
typedef struct _KS_DVD_YCrCb {
  UCHAR Reserved;
  UCHAR Y;
  UCHAR Cr;
  UCHAR Cb;
} KS_DVD_YCrCb, *PKS_DVD_YCrCb;
````

## Members


`Reserved`

Reserved. Do not use.

`Y`

Indicates the luminance (brightness) component of the color.

`Cr`

Indicates the color-red (chrominance) component of the color.

`Cb`

Indicates the color-blue (chrominance) component of the color.

## Remarks
The KS_DVD_YCrCb structure is used

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="..\ksmedia\ns-ksmedia-_ks_dvd_yuv.md">KS_DVD_YUV</a>