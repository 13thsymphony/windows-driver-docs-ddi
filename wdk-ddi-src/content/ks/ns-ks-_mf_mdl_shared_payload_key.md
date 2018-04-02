---
UID: NS:ks._MF_MDL_SHARED_PAYLOAD_KEY
title: "_MF_MDL_SHARED_PAYLOAD_KEY"
author: windows-driver-content
description: This union is used internally by the operating system.
old-location: stream\mf_mdl_shared_payload_key.htm
old-project: stream
ms.assetid: 3EA093AB-1D23-4744-997E-8C7072934628
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PMF_MDL_SHARED_PAYLOAD_KEY, MF_MDL_SHARED_PAYLOAD_KEY, MF_MDL_SHARED_PAYLOAD_KEY union [Streaming Media Devices], PMF_MDL_SHARED_PAYLOAD_KEY, PMF_MDL_SHARED_PAYLOAD_KEY union [Streaming Media Devices], _MF_MDL_SHARED_PAYLOAD_KEY, ks/MF_MDL_SHARED_PAYLOAD_KEY, ks/PMF_MDL_SHARED_PAYLOAD_KEY, stream.mf_mdl_shared_payload_key"
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
-	MF_MDL_SHARED_PAYLOAD_KEY
product:
- Windows
targetos: Windows
req.typenames: MF_MDL_SHARED_PAYLOAD_KEY, *PMF_MDL_SHARED_PAYLOAD_KEY
---

# _MF_MDL_SHARED_PAYLOAD_KEY structure
This union is used internally by the operating system.

## Syntax
```
typedef struct _MF_MDL_SHARED_PAYLOAD_KEY {
  struct {
    ULONG   fHandle;
    ULONG   pHandle;
    ULONG64 uPayload;
  } combined;
  GUID   GMDLHandle;
} MF_MDL_SHARED_PAYLOAD_KEY, *PMF_MDL_SHARED_PAYLOAD_KEY;
```

## Members


`combined`

This member is used internally by the operating system.



#### pHandle

This member is used internally by the operating system.



#### fHandle

This member is used internally by the operating system.



#### uPayload

This member is used internally by the operating system.

`GMDLHandle`

This structure is used internally by the operating system.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |