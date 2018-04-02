---
UID: NS:ksmedia.KSWAVE_VOLUME
title: KSWAVE_VOLUME
author: windows-driver-content
description: The KSWAVE_VOLUME structure is used to describe sample volume.
old-location: stream\kswave_volume.htm
old-project: stream
ms.assetid: bf3a0b49-ecec-4e96-bf09-b269e8852422
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSWAVE_VOLUME, KSWAVE_VOLUME, KSWAVE_VOLUME structure [Streaming Media Devices], PKSWAVE_VOLUME, PKSWAVE_VOLUME structure pointer [Streaming Media Devices], dvdref_602cb4a7-2e70-43a1-8e1a-7604d5b48bc1.xml, ksmedia/KSWAVE_VOLUME, ksmedia/PKSWAVE_VOLUME, stream.kswave_volume"
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
-	KSWAVE_VOLUME
product:
- Windows
targetos: Windows
req.typenames: KSWAVE_VOLUME, *PKSWAVE_VOLUME
---

# KSWAVE_VOLUME structure
The KSWAVE_VOLUME structure is used to describe sample volume.

## Syntax
```
typedef struct KSWAVE_VOLUME {
  LONG LeftAttenuation;
  LONG RightAttenuation;
} *PKSWAVE_VOLUME, KSWAVE_VOLUME;
```

## Members


`LeftAttenuation`

Specifies the amount of left attenuation.

`RightAttenuation`

Specifies the amount of right attenuation.

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566529">KSPROPERTY_WAVE_VOLUME</a> property.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566529">KSPROPERTY_WAVE_VOLUME</a>