---
UID: NS:ksmedia.KSPROPERTY_TUNER_STANDARD_MODE_S
title: KSPROPERTY_TUNER_STANDARD_MODE_S
author: windows-driver-content
description: The KSPROPERTY_TUNER_STANDARD_MODE_S structure describes whether the tuning device can identify the tuner standard from the signal itself.
old-location: stream\ksproperty_tuner_standard_mode_s.htm
old-project: stream
ms.assetid: 5f725332-155d-484f-8eaf-b45e0d7413e7
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSPROPERTY_TUNER_STANDARD_MODE_S, KSPROPERTY_TUNER_STANDARD_MODE_S, KSPROPERTY_TUNER_STANDARD_MODE_S structure [Streaming Media Devices], PKSPROPERTY_TUNER_STANDARD_MODE_S, PKSPROPERTY_TUNER_STANDARD_MODE_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TUNER_STANDARD_MODE_S, ksmedia/PKSPROPERTY_TUNER_STANDARD_MODE_S, stream.ksproperty_tuner_standard_mode_s, vidcapstruct_5b923a0a-26a2-4ef4-82d7-de7b3c3b67d0.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the operating system.
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
-	KSPROPERTY_TUNER_STANDARD_MODE_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_TUNER_STANDARD_MODE_S, *PKSPROPERTY_TUNER_STANDARD_MODE_S
---

# KSPROPERTY_TUNER_STANDARD_MODE_S structure
The KSPROPERTY_TUNER_STANDARD_MODE_S structure describes whether the tuning device can identify the tuner standard from the signal itself.

## Syntax
```
typedef struct KSPROPERTY_TUNER_STANDARD_MODE_S {
  KSPROPERTY Property;
  BOOL       AutoDetect;
} *PKSPROPERTY_TUNER_STANDARD_MODE_S, KSPROPERTY_TUNER_STANDARD_MODE_S;
```

## Members


`Property`

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property set, property ID, and request type.

`AutoDetect`

A Boolean value that indicates whether the tuning device can automatically detect the tuner standard from the signal. <b>TRUE</b> indicates that the tuning device can automatically detect the tuner standard from the signal. <b>FALSE</b> indicates that the tuning device cannot automatically detect the tuner standard.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the operating system. Available in Windows Vista and later versions of the operating system. |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565909">KSPROPERTY_TUNER_STANDARD_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567800">PROPSETID_TUNER</a>