---
UID: NS:strmini._STREAM_TIME_REFERENCE
title: "_STREAM_TIME_REFERENCE"
author: windows-driver-content
description: "."
old-location: stream\stream_time_reference.htm
old-project: stream
ms.assetid: BC3839C0-AED6-470D-9C2B-B1529B2B3D1A
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: strmini/PSTREAM_TIME_REFERENCE, STREAM_TIME_REFERENCE, *PSTREAM_TIME_REFERENCE, stream.stream_time_reference, strmini/STREAM_TIME_REFERENCE, _STREAM_TIME_REFERENCE, PSTREAM_TIME_REFERENCE structure pointer [Streaming Media Devices], PSTREAM_TIME_REFERENCE, STREAM_TIME_REFERENCE structure [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: strmini.h
req.include-header: 
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
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Strmini.h
apiname:
-	STREAM_TIME_REFERENCE
product: Windows
targetos: Windows
req.typenames: STREAM_TIME_REFERENCE, *PSTREAM_TIME_REFERENCE
req.product: Windows 10 or later.
---

# _STREAM_TIME_REFERENCE structure


## Syntax
````
typedef struct _STREAM_TIME_REFERENCE {
  STREAM_TIMESTAMP CurrentOnboardClockValue;
  LARGE_INTEGER    OnboardClockFrequency;
  LARGE_INTEGER    CurrentSystemTime;
  ULONG            Reserved[2];
} STREAM_TIME_REFERENCE, *PSTREAM_TIME_REFERENCE;
````

## Members


`CurrentOnboardClockValue`

Current value of the adapter clock.

`CurrentSystemTime`

KeQueryPerformanceCounter time.

`OnboardClockFrequency`

Frequency of the adapter clock.

`Reserved`

Reserved for future use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | strmini.h |