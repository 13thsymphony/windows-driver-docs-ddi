---
UID: NS:ksmedia.KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S
title: KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S
author: windows-driver-content
description: The KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S structure specifies the width and height of an overlay surface.
old-location: stream\ksproperty_allocator_control_surface_size_s.htm
old-project: stream
ms.assetid: 2ed72182-b098-43a6-a327-a8d81ab66309
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S, KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S, KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S structure [Streaming Media Devices], PKSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S, PKSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S, ksmedia/PKSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S, stream.ksproperty_allocator_control_surface_size_s, vidcapstruct_3ad4116b-8e7c-4249-ba27-78a387706d5b.xml"
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
-	KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S, *PKSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S
---

# KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S structure
The KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S structure specifies the width and height of an overlay surface.

## Syntax
```
typedef struct KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S {
  ULONG CX;
  ULONG CY;
}  *PKSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE_S;
```

## Members


`CX`

Specifies the width of the overlay surface.

`CY`

Specifies the height of the overlay surface


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564278">KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567792">PROPSETID_ALLOCATOR_CONTROL</a>