---
UID: NS:smclib._T0_DATA
title: "_T0_DATA"
author: windows-driver-content
description: The T0_DATA structure is used by the smart card driver library to process T0 I/O.
old-location: smartcrd\t0_data.htm
old-project: smartcrd
ms.assetid: CC827018-F6B2-48DF-BF0A-36654F866BD9
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PT0_DATA, PT0_DATA, PT0_DATA structure pointer [Smart Card Reader Devices], T0_DATA, T0_DATA structure [Smart Card Reader Devices], _T0_DATA, smartcrd.t0_data, smclib/PT0_DATA, smclib/T0_DATA"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: smclib.h
req.include-header: Smclib.h
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
-	Smclib.h
api_name:
-	T0_DATA
product:
- Windows
targetos: Windows
req.typenames: T0_DATA, *PT0_DATA
req.product: Windows 10 or later.
---

# _T0_DATA structure
The T0_DATA structure is used by the smart card driver library to process T0 I/O.

## Syntax
```
typedef struct _T0_DATA {
  ULONG Lc;
  ULONG Le;
} T0_DATA, *PT0_DATA;
```

## Members


`Lc`

Number of data bytes in the request.

`Le`

Number of expected bytes from the card.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | smclib.h (include Smclib.h) |