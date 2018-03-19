---
UID: NS:ksmedia._KSMPEGVID_RECT
title: "_KSMPEGVID_RECT"
author: windows-driver-content
description: KSMPEGVID_RECT structure
old-location: stream\ksmpegvid_rect.htm
old-project: stream
ms.assetid: 3fde33d4-a9c8-4647-bd2d-3da66f13ef8a
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSMPEGVID_RECT, KSMPEGVID_RECT, KSMPEGVID_RECT structure [Streaming Media Devices], PKSMPEGVID_RECT, PKSMPEGVID_RECT structure pointer [Streaming Media Devices], _KSMPEGVID_RECT, ksmedia/KSMPEGVID_RECT, ksmedia/PKSMPEGVID_RECT, stream.ksmpegvid_rect, vidcapstruct_ceaab9c9-ac63-4248-9365-fd9694a0b440.xml"
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
-	KSMPEGVID_RECT
product: Windows
targetos: Windows
req.typenames: KSMPEGVID_RECT, *PKSMPEGVID_RECT
---

# _KSMPEGVID_RECT structure


## Syntax
````
typedef struct _KSMPEGVID_RECT {
  ULONG StartX;
  ULONG StartY;
  ULONG EndX;
  ULONG EndY;
} KSMPEGVID_RECT, *PKSMPEGVID_RECT;
````

## Members


`StartX`



`StartY`



`EndX`



`EndY`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |