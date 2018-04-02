---
UID: NS:bdatypes._BDA_SCAN_START
title: "_BDA_SCAN_START"
author: windows-driver-content
description: "."
old-location: stream\bda_scan_start.htm
old-project: stream
ms.assetid: 931CC532-BC46-4B64-B6BA-29D20827EC0A
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PBDA_SCAN_START, BDA_SCAN_START, BDA_SCAN_START structure [Streaming Media Devices], PBDA_SCAN_START, PBDA_SCAN_START structure pointer [Streaming Media Devices], _BDA_SCAN_START, bdatypes/BDA_SCAN_START, bdatypes/PBDA_SCAN_START, stream.bda_scan_start"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdatypes.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Bdatypes.h
api_name:
-	BDA_SCAN_START
product: Windows
targetos: Windows
req.typenames: BDA_SCAN_START, *PBDA_SCAN_START
---

# _BDA_SCAN_START structure


## Syntax
```
typedef struct _BDA_SCAN_START {
  PBDARESULT lResult;
  ULONG      LowerFrequency;
  ULONG      HigerFrequency;
} BDA_SCAN_START, *PBDA_SCAN_START;
```

## Members


`lResult`



`LowerFrequency`



`HigerFrequency`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | bdatypes.h |