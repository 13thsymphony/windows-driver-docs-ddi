---
UID : NE:ksmedia.KS_AMPixAspectRatio
title : KS_AMPixAspectRatio
author : windows-driver-content
description : The KS_AMPixAspectRatio enumeration defines the pixel aspect ratio that corresponds to a 720 480 NTSC video signal or a 720 × 576 PAL video signal.
old-location : stream\ks_ampixaspectratio.htm
old-project : stream
ms.assetid : 29c84529-11f6-429b-81c6-96d6a1773b3b
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ksmedia/KS_PixAspectRatio_NTSC16x9, KS_PixAspectRatio_NTSC16x9, KS_PixAspectRatio_PAL4x3, KS_AMPixAspectRatio, ksmedia/KS_PixAspectRatio_PAL4x3, ksmedia/KS_AMPixAspectRatio, KS_PixAspectRatio_PAL16x9, ksmedia/KS_PixAspectRatio_NTSC4x3, KS_PixAspectRatio_NTSC4x3, ksmedia/KS_PixAspectRatio_PAL16x9, KS_AMPixAspectRatio enumeration [Streaming Media Devices], vidcapstruct_d891dbda-a467-4e13-bad6-fef794146717.xml, stream.ks_ampixaspectratio
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
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
req.typenames : KS_AMPixAspectRatio
---

# KS_AMPixAspectRatio Enumeration
The KS_AMPixAspectRatio enumeration defines the pixel aspect ratio that corresponds to a 720  480 NTSC video signal or a 720 × 576 PAL video signal.

## Syntax
````
typedef enum  { 
  KS_PixAspectRatio_NTSC4x3   = 0,
  KS_PixAspectRatio_NTSC16x9  = 1,
  KS_PixAspectRatio_PAL4x3    = 2,
  KS_PixAspectRatio_PAL16x9   = 3
} KS_AMPixAspectRatio;
````

## Constants

<table>

<tr>
<td>KS_PixAspectRatio_NTSC16x9</td>
<td>Specifies a 16 × 9 NTSC pixel aspect ratio.</td>
</tr>

<tr>
<td>KS_PixAspectRatio_NTSC4x3</td>
<td>Specifies a 4 × 3 NTSC pixel aspect ratio.</td>
</tr>

<tr>
<td>KS_PixAspectRatio_PAL16x9</td>
<td>Specifies a 16 × 9 PAL pixel aspect ratio.</td>
</tr>

<tr>
<td>KS_PixAspectRatio_PAL4x3</td>
<td>Specifies a 4 × 3 PAL pixel aspect ratio.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h (include Ksmedia.h) |