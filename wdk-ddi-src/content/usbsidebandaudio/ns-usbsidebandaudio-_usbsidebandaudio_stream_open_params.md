---
UID: NS:usbsidebandaudio._USBSIDEBANDAUDIO_STREAM_OPEN_PARAMS
title: "_USBSIDEBANDAUDIO_STREAM_OPEN_PARAMS"
author: windows-driver-content
description: TBD.
old-location: audio\usbsidebandaudio_stream_open_params.htm
old-project: audio
ms.assetid: B7FFCD5B-ED00-4B56-806F-61AB43481578
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: "*PUSBSIDEBANDAUDIO_STREAM_OPEN_PARAMS, USBSIDEBANDAUDIO_STREAM_OPEN_PARAMS structure [Audio Devices], audio.usbsidebandaudio_stream_open_params, USBSIDEBANDAUDIO_STREAM_OPEN_PARAMS, PUSBSIDEBANDAUDIO_STREAM_OPEN_PARAMS structure pointer [Audio Devices], PUSBSIDEBANDAUDIO_STREAM_OPEN_PARAMS, usbsidebandaudio/PUSBSIDEBANDAUDIO_STREAM_OPEN_PARAMS, _USBSIDEBANDAUDIO_STREAM_OPEN_PARAMS, usbsidebandaudio/USBSIDEBANDAUDIO_STREAM_OPEN_PARAMS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbsidebandaudio.h
req.include-header: Usbsidebandaudio.h
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
-	kbSyntax
apitype:
-	<TBD>
apilocation:
-
apiname:
-	USBSIDEBANDAUDIO_STREAM_OPEN_PARAMS
product: Windows
targetos: Windows
req.typenames: "*PUSBSIDEBANDAUDIO_STREAM_OPEN_PARAMS, USBSIDEBANDAUDIO_STREAM_OPEN_PARAMS"
req.product: Windows 10 or later.
---

# _USBSIDEBANDAUDIO_STREAM_OPEN_PARAMS structure
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

TBD

## Syntax
````
typedef struct _USBSIDEBANDAUDIO_STREAM_OPEN_PARAMS {
  ULONG                             Reserved 0;
  KSDATAFORMAT_WAVEFORMATEXTENSIBLE Reserved 1;
} USBSIDEBANDAUDIO_STREAM_OPEN_PARAMS, *PUSBSIDEBANDAUDIO_STREAM_OPEN_PARAMS;
````

## Members


`EpIndex`



`Format`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbsidebandaudio.h (include Usbsidebandaudio.h) |