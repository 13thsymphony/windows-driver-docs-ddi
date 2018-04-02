---
UID: NS:ks.KSPROPERTY_SERIALHDR
title: KSPROPERTY_SERIALHDR
author: windows-driver-content
description: The format of the serialization buffer is a KSPROPERTY_SERIALHDR structure, followed by serialized properties.
old-location: stream\ksproperty_serialhdr.htm
old-project: stream
ms.assetid: 164c34ce-603f-447b-8bd7-14b1c19e9baa
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSPROPERTY_SERIALHDR, KSPROPERTY_SERIALHDR, KSPROPERTY_SERIALHDR structure [Streaming Media Devices], PKSPROPERTY_SERIALHDR, PKSPROPERTY_SERIALHDR structure pointer [Streaming Media Devices], ks-struct_cdf54d37-a5b8-4a73-98dd-c7a9439ac51a.xml, ks/KSPROPERTY_SERIALHDR, ks/PKSPROPERTY_SERIALHDR, stream.ksproperty_serialhdr"
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
-	KSPROPERTY_SERIALHDR
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_SERIALHDR, *PKSPROPERTY_SERIALHDR
---

# KSPROPERTY_SERIALHDR structure
The format of the serialization buffer is a KSPROPERTY_SERIALHDR structure, followed by serialized properties.

## Syntax
```
typedef struct KSPROPERTY_SERIALHDR {
  GUID  PropertySet;
  ULONG Count;
} *PKSPROPERTY_SERIALHDR, KSPROPERTY_SERIALHDR;
```

## Members


`PropertySet`

Specifies the GUID of the property set contained in the serialized buffer.

`Count`

Specifies the count of serialized properties to follow.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565224">KSPROPERTY_SERIAL</a>