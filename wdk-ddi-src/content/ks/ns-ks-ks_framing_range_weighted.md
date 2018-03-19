---
UID: NS:ks.KS_FRAMING_RANGE_WEIGHTED
title: KS_FRAMING_RANGE_WEIGHTED
author: windows-driver-content
description: Drivers can use the KS_FRAMING_RANGE_WEIGHTED structure to specify a range of weighted frame sizes.
old-location: stream\ks_framing_range_weighted.htm
old-project: stream
ms.assetid: a52cde43-f440-4e58-97b7-b2aac5fb5f6a
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKS_FRAMING_RANGE_WEIGHTED, KS_FRAMING_RANGE_WEIGHTED, KS_FRAMING_RANGE_WEIGHTED structure [Streaming Media Devices], PKS_FRAMING_RANGE_WEIGHTED, PKS_FRAMING_RANGE_WEIGHTED structure pointer [Streaming Media Devices], ks-struct_9bc7dcda-b095-4f53-9446-40ec43d6397b.xml, ks/KS_FRAMING_RANGE_WEIGHTED, ks/PKS_FRAMING_RANGE_WEIGHTED, stream.ks_framing_range_weighted"
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
-	KS_FRAMING_RANGE_WEIGHTED
product: Windows
targetos: Windows
req.typenames: KS_FRAMING_RANGE_WEIGHTED, *PKS_FRAMING_RANGE_WEIGHTED
---

# KS_FRAMING_RANGE_WEIGHTED structure
Drivers can use the KS_FRAMING_RANGE_WEIGHTED structure to specify a range of weighted frame sizes.

## Syntax
````
typedef struct {
  KS_FRAMING_RANGE Range;
  ULONG            InPlaceWeight;
  ULONG            NotInPlaceWeight;
} KS_FRAMING_RANGE_WEIGHTED, *PKS_FRAMING_RANGE_WEIGHTED;
````

## Members


`Range`

Specifies the framing range.

`InPlaceWeight`

Not currently supported. Drivers should set to zero.

`NotInPlaceWeight`

Not currently supported. Drivers should set to zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="..\ks\ns-ks-ks_framing_item.md">KS_FRAMING_ITEM</a>