---
UID: NS:usbsidebandaudio._USBSIDEBANDAUDIO_DEVICE_ERROR
title: "_USBSIDEBANDAUDIO_DEVICE_ERROR"
author: windows-driver-content
description: TBD.
old-location: audio\usbsidebandaudio_device_error.htm
old-project: audio
ms.assetid: EB5AFAF3-D75C-4B91-823C-E1C6784CB13B
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: "*PUSBSIDEBANDAUDIO_DEVICE_ERROR, PUSBSIDEBANDAUDIO_DEVICE_ERROR, PUSBSIDEBANDAUDIO_DEVICE_ERROR structure pointer [Audio Devices], USBSIDEBANDAUDIO_DEVICE_ERROR, USBSIDEBANDAUDIO_DEVICE_ERROR structure [Audio Devices], _USBSIDEBANDAUDIO_DEVICE_ERROR, audio.usbsidebandaudio_device_error, usbsidebandaudio/PUSBSIDEBANDAUDIO_DEVICE_ERROR, usbsidebandaudio/USBSIDEBANDAUDIO_DEVICE_ERROR"
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
topic_type:
-	kbSyntax
api_type:
-	<TBD>
api_location:
-
api_name:
-	USBSIDEBANDAUDIO_DEVICE_ERROR
product: Windows
targetos: Windows
req.typenames: USBSIDEBANDAUDIO_DEVICE_ERROR, *PUSBSIDEBANDAUDIO_DEVICE_ERROR
req.product: Windows 10 or later.
---

# _USBSIDEBANDAUDIO_DEVICE_ERROR structure
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

TBD

## Syntax
```
typedef struct _USBSIDEBANDAUDIO_DEVICE_ERROR {
  ULONG    EpIndex;
  bool     Immediate;
  NTSTATUS Status;
} USBSIDEBANDAUDIO_DEVICE_ERROR, *PUSBSIDEBANDAUDIO_DEVICE_ERROR;
```

## Members


`EpIndex`



`Immediate`



`Status`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbsidebandaudio.h (include Usbsidebandaudio.h) |