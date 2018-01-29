---
UID : NS:usbsidebandaudio._USBSIDEBANDAUDIO_VOLUME_PARAMS
title : _USBSIDEBANDAUDIO_VOLUME_PARAMS
author : windows-driver-content
description : TBD.
old-location : audio\usbsidebandaudio_volume_params.htm
old-project : audio
ms.assetid : 253CD4CB-AC8D-4CA0-B620-EB1CC4DFD925
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : PUSBSIDEBANDAUDIO_VOLUME_PARAMS structure pointer [Audio Devices], usbsidebandaudio/USBSIDEBANDAUDIO_VOLUME_PARAMS, audio.usbsidebandaudio_volume_params, _USBSIDEBANDAUDIO_VOLUME_PARAMS, PUSBSIDEBANDAUDIO_VOLUME_PARAMS, *PUSBSIDEBANDAUDIO_VOLUME_PARAMS, USBSIDEBANDAUDIO_VOLUME_PARAMS structure [Audio Devices], usbsidebandaudio/PUSBSIDEBANDAUDIO_VOLUME_PARAMS, USBSIDEBANDAUDIO_VOLUME_PARAMS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : usbsidebandaudio.h
req.include-header : Usbsidebandaudio.h
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
req.typenames : "*PUSBSIDEBANDAUDIO_VOLUME_PARAMS, USBSIDEBANDAUDIO_VOLUME_PARAMS"
req.product : Windows 10 or later.
---

# _USBSIDEBANDAUDIO_VOLUME_PARAMS structure
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

TBD

## Syntax
````
typedef struct _USBSIDEBANDAUDIO_VOLUME_PARAMS {
  ULONG Reserved 0;
  BOOL  Reserved 1;
  LONG  Reserved 2;
} USBSIDEBANDAUDIO_VOLUME_PARAMS, *PUSBSIDEBANDAUDIO_VOLUME_PARAMS;
````

## Members


`EpIndex`



`Immediate`



`Value`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | usbsidebandaudio.h (include Usbsidebandaudio.h) |