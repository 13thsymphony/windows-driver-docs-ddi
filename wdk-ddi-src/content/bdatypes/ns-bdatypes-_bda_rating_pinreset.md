---
UID: NS:bdatypes._BDA_RATING_PINRESET
title: "_BDA_RATING_PINRESET"
author: windows-driver-content
description: "."
old-location: stream\bda_rating_pinreset.htm
old-project: stream
ms.assetid: 237463EC-3C57-4DCA-9757-870B5F55C584
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.bda_rating_pinreset, BDA_RATING_PINRESET structure [Streaming Media Devices], bdatypes/PBDA_RATING_PINRESET, bdatypes/BDA_RATING_PINRESET, _BDA_RATING_PINRESET, BDA_RATING_PINRESET, *PBDA_RATING_PINRESET, PBDA_RATING_PINRESET structure pointer [Streaming Media Devices], PBDA_RATING_PINRESET
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Bdatypes.h
apiname:
-	BDA_RATING_PINRESET
product: Windows
targetos: Windows
req.typenames: BDA_RATING_PINRESET, *PBDA_RATING_PINRESET
---

# _BDA_RATING_PINRESET structure


## Syntax
````
typedef struct _BDA_RATING_PINRESET {
  BYTE bPinLength;
  BYTE argbNewPin[MIN_DIMENSION];
} BDA_RATING_PINRESET, *PBDA_RATING_PINRESET;
````

## Members


`argbNewPin`

Specifies null-terminated UTF8. Use an empty string if the pin is disabled.

`bPinLength`

Specifies the buffer size including a null termination.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | bdatypes.h |