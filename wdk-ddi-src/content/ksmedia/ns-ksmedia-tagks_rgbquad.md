---
UID: NS:ksmedia.tagKS_RGBQUAD
title: tagKS_RGBQUAD
author: windows-driver-content
description: The KS_RGBQUAD structure describes a color consisting of relative intensities of red, green, and blue, ranging from 0 to 255 (0x0 to 0xff).
old-location: stream\ks_rgbquad.htm
old-project: stream
ms.assetid: 49231293-286b-486d-b8f9-b44bdb845e7b
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: PKS_RGBQUAD structure pointer [Streaming Media Devices], stream.ks_rgbquad, *PKS_RGBQUAD, PKS_RGBQUAD, vidcapstruct_c081668e-9e81-4c30-89d1-b4c26dc9a300.xml, KS_RGBQUAD structure [Streaming Media Devices], ksmedia/PKS_RGBQUAD, tagKS_RGBQUAD, ksmedia/KS_RGBQUAD, KS_RGBQUAD
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
-	KS_RGBQUAD
product: Windows
targetos: Windows
req.typenames: "*PKS_RGBQUAD, KS_RGBQUAD"
---

# tagKS_RGBQUAD structure
The KS_RGBQUAD structure describes a color consisting of relative intensities of red, green, and blue, ranging from 0 to 255 (0x0 to 0xff).

## Syntax
````
typedef struct tagKS_RGBQUAD {
  BYTE rgbBlue;
  BYTE rgbGreen;
  BYTE rgbRed;
  BYTE rgbReserved;
} KS_RGBQUAD, *PKS_RGBQUAD;
````

## Members


`rgbBlue`

Specifies the intensity of blue in the color.

`rgbGreen`

Specifies the intensity of green in the color.

`rgbRed`

Specifies the intensity of red in the color.

`rgbReserved`

Reserved. This member must be zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |