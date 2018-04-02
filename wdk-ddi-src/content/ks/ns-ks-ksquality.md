---
UID: NS:ks.KSQUALITY
title: KSQUALITY
author: windows-driver-content
description: The KSQUALITY structure is used to report QM problems in both kernel and user mode to their respective quality managers.
old-location: stream\ksquality.htm
old-project: stream
ms.assetid: 36caaea9-2354-4ed8-9649-5eb102def8d5
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSQUALITY, KSQUALITY, KSQUALITY structure [Streaming Media Devices], PKSQUALITY, PKSQUALITY structure pointer [Streaming Media Devices], ks-struct_a2b63e1c-e5b4-437d-a5ba-0746f8388eef.xml, ks/KSQUALITY, ks/PKSQUALITY, stream.ksquality"
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
-	KSQUALITY
product: Windows
targetos: Windows
req.typenames: KSQUALITY, *PKSQUALITY
---

# KSQUALITY structure
The KSQUALITY structure is used to report QM problems in both kernel and user mode to their respective quality managers.

## Syntax
```
typedef struct KSQUALITY {
  PVOID    Context;
  ULONG    Proportion;
  LONGLONG DeltaTime;
}  *PKSQUALITY;
```

## Members


`Context`

Specifies a context parameter that was originally passed to the connection.

`Proportion`

Indicates the percentage of frames currently being received that are actually being used. This is expressed in units of one-tenth of a percent, where 1000 is optimal.

`DeltaTime`

Indicates the delta in native units (as indicated by the Interface) from optimal time at which the frames are being delivered, where a positive number means too late, and a negative number means too early. Zero indicates a correct delta.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |