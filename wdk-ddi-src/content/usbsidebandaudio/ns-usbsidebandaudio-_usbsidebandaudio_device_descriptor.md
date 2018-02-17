---
UID: NS:usbsidebandaudio._USBSIDEBANDAUDIO_DEVICE_DESCRIPTOR
title: "_USBSIDEBANDAUDIO_DEVICE_DESCRIPTOR"
author: windows-driver-content
description: TBD.
old-location: audio\usbsidebandaudio_device_descriptor.htm
old-project: audio
ms.assetid: 66EDD6E5-F6EB-42C9-8B68-3A19DED7DCB8
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: USBSIDEBANDAUDIO_DEVICE_DESCRIPTOR, usbsidebandaudio/PUSBSIDEBANDAUDIO_DEVICE_DESCRIPTOR, *PUSBSIDEBANDAUDIO_DEVICE_DESCRIPTOR, USBSIDEBANDAUDIO_DEVICE_DESCRIPTOR structure [Audio Devices], PUSBSIDEBANDAUDIO_DEVICE_DESCRIPTOR structure pointer [Audio Devices], usbsidebandaudio/USBSIDEBANDAUDIO_DEVICE_DESCRIPTOR, PUSBSIDEBANDAUDIO_DEVICE_DESCRIPTOR, _USBSIDEBANDAUDIO_DEVICE_DESCRIPTOR, audio.usbsidebandaudio_device_descriptor
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
-	USBSIDEBANDAUDIO_DEVICE_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: "*PUSBSIDEBANDAUDIO_DEVICE_DESCRIPTOR, USBSIDEBANDAUDIO_DEVICE_DESCRIPTOR"
req.product: Windows 10 or later.
---

# _USBSIDEBANDAUDIO_DEVICE_DESCRIPTOR structure
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

TBD

## Syntax
````
typedef struct _USBSIDEBANDAUDIO_DEVICE_DESCRIPTOR {
  ULONG Reserved 0;
  GUID  Reserved 1;
  ULONG Reserved 2;
} USBSIDEBANDAUDIO_DEVICE_DESCRIPTOR, *PUSBSIDEBANDAUDIO_DEVICE_DESCRIPTOR;
````

## Members


`CbSize`



`ContainerId`



`NumberOfEndpoints`



## Remarks
TBD

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbsidebandaudio.h (include Usbsidebandaudio.h) |