---
UID: NS:usbsidebandaudio._USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION
title: "_USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION"
author: windows-driver-content
description: TBD.
old-location: audio\usbsidebandaudio_ep_shadow_resources_function.htm
old-project: audio
ms.assetid: 554C5829-D9C0-4F5F-B88A-285A31415CD3
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: "_USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION, usbsidebandaudio/USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION, USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION, *PUSBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION, usbsidebandaudio/PUSBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION, PUSBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION structure pointer [Audio Devices], audio.usbsidebandaudio_ep_shadow_resources_function, USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION structure [Audio Devices], PUSBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION"
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
-	USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION
product: Windows
targetos: Windows
req.typenames: "*PUSBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION, USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION"
req.product: Windows 10 or later.
---

# _USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION structure
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

TBD

## Syntax
````
typedef struct _USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION {
  ULONG                    Reserved 0;
  PUSB_ENDPOINT_DESCRIPTOR Reserved 1;
  USHORT                   Reserved 2;
  UCHAR                    Reserved 3;
  UCHAR                    Reserved 4;
} USBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION, *PUSBSIDEBANDAUDIO_EP_SHADOW_RESOURCES_FUNCTION;
````

## Members


`bcdAudioSpec`



`bDelay`



`bSlotSize`



`CbSize`



`pUsbEndpointDescriptor`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbsidebandaudio.h (include Usbsidebandaudio.h) |