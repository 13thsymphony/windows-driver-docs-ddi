---
UID: NS:ks.KSSTREAM_UVC_METADATA
title: KSSTREAM_UVC_METADATA
author: windows-driver-content
description: The KSSTREAM_UVC_METADATA structure contains start and end of frame timestamp information.
old-location: stream\ksstream_uvc_metadata.htm
old-project: stream
ms.assetid: 99ED5E06-23C7-4B24-BD9B-E6713B1D58D2
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSSTREAM_UVC_METADATA, KSSTREAM_UVC_METADATA, KSSTREAM_UVC_METADATA structure [Streaming Media Devices], PKSSTREAM_UVC_METADATA, PKSSTREAM_UVC_METADATA structure pointer [Streaming Media Devices], ks/KSSTREAM_UVC_METADATA, ks/PKSSTREAM_UVC_METADATA, stream.ksstream_uvc_metadata"
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
-	KSSTREAM_UVC_METADATA
product: Windows
targetos: Windows
req.typenames: KSSTREAM_UVC_METADATA, *PKSSTREAM_UVC_METADATA
---

# KSSTREAM_UVC_METADATA structure
The <b>KSSTREAM_UVC_METADATA</b> structure contains start and end of frame timestamp information.

## Syntax
```
typedef struct KSSTREAM_UVC_METADATA {
  KSSTREAM_UVC_METADATATYPE_TIMESTAMP StartOfFrameTimestamp;
  KSSTREAM_UVC_METADATATYPE_TIMESTAMP EndOfFrameTimestamp;
}  *PKSSTREAM_UVC_METADATA;
```

## Members


`StartOfFrameTimestamp`

Contains  start of frame timestamp information.

`EndOfFrameTimestamp`

Contains end of frame timestamp information.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |