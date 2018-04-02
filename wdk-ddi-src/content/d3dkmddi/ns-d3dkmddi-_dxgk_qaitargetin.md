---
UID: NS:d3dkmddi._DXGK_QAITARGETIN
title: "_DXGK_QAITARGETIN"
author: windows-driver-content
description: Used to integrate a target.
old-location: display\dxgk_qaitargetin.htm
old-project: display
ms.assetid: C6751CB1-1460-4C1A-9E5F-99448C4F9162
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_QAITARGETIN, DXGK_QAITARGETIN structure [Display Devices], DXGK_QUERYCOLORIMETRYOVERRIDESIN, DXGK_QUERYINTEGRATEDDISPLAYIN, _DXGK_QAITARGETIN, d3dkmddi/DXGK_QAITARGETIN, display.dxgk_qaitargetin
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
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
-	d3dkmddi.h
api_name:
-	DXGK_QAITARGETIN
product: Windows
targetos: Windows
req.typenames: DXGK_QAITARGETIN
---

# _DXGK_QAITARGETIN structure
Used to integrate a target.

## Syntax
```
typedef struct _DXGK_QAITARGETIN {
  D3DDDI_VIDEO_PRESENT_TARGET_ID TargetId;
} DXGK_QAITARGETIN;
```

## Members


`TargetId`

The ID of the target.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmddi.h |