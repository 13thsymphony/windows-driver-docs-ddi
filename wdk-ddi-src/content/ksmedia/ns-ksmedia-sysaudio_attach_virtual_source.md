---
UID: NS:ksmedia.SYSAUDIO_ATTACH_VIRTUAL_SOURCE
title: SYSAUDIO_ATTACH_VIRTUAL_SOURCE
author: windows-driver-content
description: The SYSAUDIO_ATTACH_VIRTUAL_SOURCE structure is used to attach a mixer-line virtual source (for example, a volume or mute control) to a mixer pin on the virtual audio device.
old-location: audio\sysaudio_attach_virtual_source.htm
old-project: audio
ms.assetid: 1215cf8e-8e94-4da4-9fb9-2212e8386abd
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PSYSAUDIO_ATTACH_VIRTUAL_SOURCE, PSYSAUDIO_ATTACH_VIRTUAL_SOURCE, PSYSAUDIO_ATTACH_VIRTUAL_SOURCE structure pointer [Audio Devices], SYSAUDIO_ATTACH_VIRTUAL_SOURCE, SYSAUDIO_ATTACH_VIRTUAL_SOURCE structure [Audio Devices], aud-prop_5fce938d-a784-46cf-a65b-3eb0d19db2f8.xml, audio.sysaudio_attach_virtual_source, ksmedia/PSYSAUDIO_ATTACH_VIRTUAL_SOURCE, ksmedia/SYSAUDIO_ATTACH_VIRTUAL_SOURCE"
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
-	SYSAUDIO_ATTACH_VIRTUAL_SOURCE
product: Windows
targetos: Windows
req.typenames: SYSAUDIO_ATTACH_VIRTUAL_SOURCE, *PSYSAUDIO_ATTACH_VIRTUAL_SOURCE
---

# SYSAUDIO_ATTACH_VIRTUAL_SOURCE structure
The SYSAUDIO_ATTACH_VIRTUAL_SOURCE structure is used to attach a mixer-line virtual source (for example, a volume or mute control) to a mixer pin on the virtual audio device.

## Syntax
````
typedef struct {
  KSPROPERTY Property;
  ULONG      MixerPinId;
  ULONG      Reserved;
} SYSAUDIO_ATTACH_VIRTUAL_SOURCE, *PSYSAUDIO_ATTACH_VIRTUAL_SOURCE;
````

## Members


`Property`

Specifies the property. This parameter is a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>.

`MixerPinId`

Specifies the virtual source index.

`Reserved`

Reserved. Set to zero.

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537413">KSPROPERTY_SYSAUDIO_ATTACH_VIRTUAL_SOURCE</a> property.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537413">KSPROPERTY_SYSAUDIO_ATTACH_VIRTUAL_SOURCE</a>