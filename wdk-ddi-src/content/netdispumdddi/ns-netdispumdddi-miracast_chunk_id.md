---
UID: NS:netdispumdddi.MIRACAST_CHUNK_ID
title: MIRACAST_CHUNK_ID
author: windows-driver-content
description: Stores info that identifies a wireless display (Miracast) encode chunk.
old-location: display\miracast_chunk_id.htm
old-project: display
ms.assetid: 30140530-63B6-4FE4-98A4-C6950D7D4D9A
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: netdispumdddi/MIRACAST_CHUNK_ID, MIRACAST_CHUNK_ID, display.miracast_chunk_id, MIRACAST_CHUNK_ID union [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
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
-	Netdispumdddi.h
apiname:
-	MIRACAST_CHUNK_ID
product: Windows
targetos: Windows
req.typenames: MIRACAST_CHUNK_ID
---

# MIRACAST_CHUNK_ID structure
Stores info that identifies a wireless display (Miracast) encode chunk.

## Syntax
````
typedef union {
  struct {
    UINT64 FrameNumber  :40;
    UINT64 PartNumber  :24;
  };
  UINT64 Value;
} MIRACAST_CHUNK_ID;
````

## Members


`Value`

Holds a 64-bit value that identifies the encode chunk.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | netdispumdddi.h (include Netdispumdddi.h) |