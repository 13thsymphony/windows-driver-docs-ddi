---
UID: NS:ks.KSP_PIN
title: KSP_PIN
author: windows-driver-content
description: Kernel streaming clients use the KSP_PIN structure to specify the property and pin type within a KSPROPSETID_Pin property request.
old-location: stream\ksp_pin.htm
old-project: stream
ms.assetid: 0be4c4e1-6ea6-4439-841d-088cb1902604
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSP_PIN, KSPROPERTY_PIN_FLAGS_ATTRIBUTE_RANGE_AWARE, KSP_PIN, KSP_PIN structure [Streaming Media Devices], PKSP_PIN, PKSP_PIN structure pointer [Streaming Media Devices], ks-struct_02faf16f-fb8d-4f1f-9176-e2c379a36d4e.xml, ks/KSP_PIN, ks/PKSP_PIN, stream.ksp_pin"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
api_name:
-	KSP_PIN
product:
- Windows
targetos: Windows
req.typenames: KSP_PIN, *PKSP_PIN
---

# KSP_PIN structure
Kernel streaming clients use the KSP_PIN structure to specify the property and pin type within a KSPROPSETID_Pin property request.

## Syntax
```
typedef struct KSP_PIN {
  KSPROPERTY Property;
  ULONG      PinId;
  union {
    ULONG Flags;
    ULONG Reserved;
  };
} *PKSP_PIN, KSP_PIN;
```

## Members


`Property`

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure.

`PinId`

Specifies the pin type ID.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>