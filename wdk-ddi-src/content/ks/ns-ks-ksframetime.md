---
UID: NS:ks.KSFRAMETIME
title: KSFRAMETIME
author: windows-driver-content
description: The KSFRAMETIME structure is supported by rendering pins, and is used to return the duration of the next &#0034;frame&#0034; of data, and flags associated with that frame.
old-location: stream\ksframetime.htm
old-project: stream
ms.assetid: 0e3beb72-2b00-41be-a7b4-341bcf065e92
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSFRAMETIME, KSFRAMETIME, KSFRAMETIME structure [Streaming Media Devices], PKSFRAMETIME, PKSFRAMETIME structure pointer [Streaming Media Devices], ks-struct_3abc9b81-d7e7-455c-a577-2efa7c986cc5.xml, ks/KSFRAMETIME, ks/PKSFRAMETIME, stream.ksframetime"
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
-	KSFRAMETIME
product: Windows
targetos: Windows
req.typenames: KSFRAMETIME, *PKSFRAMETIME
---

# KSFRAMETIME structure
The KSFRAMETIME structure is supported by rendering pins, and is used to return the duration of the next "frame" of data, and flags associated with that frame.

## Syntax
```
typedef struct KSFRAMETIME {
  LONGLONG Duration;
  ULONG    FrameFlags;
  ULONG    Reserved;
}  *PKSFRAMETIME;
```

## Members


`Duration`

Specifies the duration in presentation time units.

`FrameFlags`

Specifies the flags specific to the next frame, or to all frames. Flags are described on the reference page for <a href="https://msdn.microsoft.com/library/windows/hardware/ff560979">KSALLOCATOR_FRAMING</a>.

`Reserved`

Set to zero.

## Remarks
Note that this is an optional property, which need only be implemented if the pin instance understands the specifics of the media type it is transporting.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |