---
UID: NE:ksmedia.KS_VIDEODECODER_FLAGS
title: KS_VIDEODECODER_FLAGS
author: windows-driver-content
description: The KS_VIDEODECODER_FLAGS enumeration defines video decoder capabilities.
old-location: stream\ks_videodecoder_flags.htm
old-project: stream
ms.assetid: 120d7714-8c32-4b83-adc2-c9a933e541e5
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KS_VIDEODECODER_FLAGS, KS_VIDEODECODER_FLAGS enumeration [Streaming Media Devices], KS_VIDEODECODER_FLAGS_CAN_DISABLE_OUTPUT, KS_VIDEODECODER_FLAGS_CAN_INDICATE_LOCKED, KS_VIDEODECODER_FLAGS_CAN_USE_VCR_LOCKING, ksmedia/KS_VIDEODECODER_FLAGS, ksmedia/KS_VIDEODECODER_FLAGS_CAN_DISABLE_OUTPUT, ksmedia/KS_VIDEODECODER_FLAGS_CAN_INDICATE_LOCKED, ksmedia/KS_VIDEODECODER_FLAGS_CAN_USE_VCR_LOCKING, stream.ks_videodecoder_flags, vidcapstruct_061ba371-f4a8-44b0-8940-bc90b15dbfed.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	KS_VIDEODECODER_FLAGS
product: Windows
targetos: Windows
req.typenames: KS_VIDEODECODER_FLAGS
---

# KS_VIDEODECODER_FLAGS Enumeration
The KS_VIDEODECODER_FLAGS enumeration defines video decoder capabilities.

## Syntax
````
typedef enum  { 
  KS_VIDEODECODER_FLAGS_CAN_DISABLE_OUTPUT   = 0X0001,
  KS_VIDEODECODER_FLAGS_CAN_USE_VCR_LOCKING  = 0X0002,
  KS_VIDEODECODER_FLAGS_CAN_INDICATE_LOCKED  = 0X0004
} KS_VIDEODECODER_FLAGS;
````

## Constants

<table>
            
                <tr>
                    <td>KS_VIDEODECODER_FLAGS_CAN_DISABLE_OUTPUT</td>
                    <td>The decoder can translate its output lines. Video decoders that use a video port use this flag.</td>
                </tr>
            
                <tr>
                    <td>KS_VIDEODECODER_FLAGS_CAN_USE_VCR_LOCKING</td>
                    <td>The video decoder can alter its phase locked loop (PLL) timings to lock on to noisy signals. This flag typically is used when the video source is a VCR that introduces variability in the vertical and horizontal sync timing.</td>
                </tr>
            
                <tr>
                    <td>KS_VIDEODECODER_FLAGS_CAN_INDICATE_LOCKED</td>
                    <td>The video decoder can distinguish whether it has locked to an incoming analog video signal.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="..\ksmedia\ns-ksmedia-ksproperty_videodecoder_caps_s.md">KSPROPERTY_VIDEODECODER_CAPS_S</a>