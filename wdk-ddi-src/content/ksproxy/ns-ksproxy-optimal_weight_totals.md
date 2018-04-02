---
UID: NS:ksproxy.OPTIMAL_WEIGHT_TOTALS
title: OPTIMAL_WEIGHT_TOTALS
author: windows-driver-content
description: "."
old-location: stream\optimal_weight_totals.htm
old-project: stream
ms.assetid: 56D97D0F-1934-4834-99A7-8A745A3E6757
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: OPTIMAL_WEIGHT_TOTALS, OPTIMAL_WEIGHT_TOTALS structure [Streaming Media Devices], ksproxy/OPTIMAL_WEIGHT_TOTALS, stream.optimal_weight_totals
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksproxy.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ksproxy.h
api_name:
-	OPTIMAL_WEIGHT_TOTALS
product: Windows
targetos: Windows
req.typenames: OPTIMAL_WEIGHT_TOTALS
---

# OPTIMAL_WEIGHT_TOTALS structure


## Syntax
```
typedef struct OPTIMAL_WEIGHT_TOTALS {
  LONGLONG MinTotalNominator;
  LONGLONG MaxTotalNominator;
  LONGLONG TotalDenominator;
};
```

## Members


`MinTotalNominator`



`MaxTotalNominator`



`TotalDenominator`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksproxy.h |