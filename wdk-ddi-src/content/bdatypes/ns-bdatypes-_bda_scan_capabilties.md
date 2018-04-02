---
UID: NS:bdatypes._BDA_SCAN_CAPABILTIES
title: "_BDA_SCAN_CAPABILTIES"
author: windows-driver-content
description: "."
old-location: stream\bda_scan_capabilties.htm
old-project: stream
ms.assetid: AB97C5AC-E5B8-4C2B-ADA1-73E27E4B81D5
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PBDA_SCAN_CAPABILTIES, BDA_SCAN_CAPABILTIES, BDA_SCAN_CAPABILTIES structure [Streaming Media Devices], PBDA_SCAN_CAPABILTIES, PBDA_SCAN_CAPABILTIES structure pointer [Streaming Media Devices], _BDA_SCAN_CAPABILTIES, bdatypes/BDA_SCAN_CAPABILTIES, bdatypes/PBDA_SCAN_CAPABILTIES, stream.bda_scan_capabilties"
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
-	BDA_SCAN_CAPABILTIES
product:
- Windows
targetos: Windows
req.typenames: BDA_SCAN_CAPABILTIES, *PBDA_SCAN_CAPABILTIES
---

# _BDA_SCAN_CAPABILTIES structure


## Syntax
```
typedef struct _BDA_SCAN_CAPABILTIES {
  PBDARESULT lResult;
  UINT64     ul64AnalogStandardsSupported;
} *PBDA_SCAN_CAPABILTIES, BDA_SCAN_CAPABILTIES;
```

## Members


`lResult`



`ul64AnalogStandardsSupported`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | bdatypes.h |