---
UID: NS:d3dkmthk._D3DKMT_SET_COLORSPACE_TRANSFORM
title: "_D3DKMT_SET_COLORSPACE_TRANSFORM"
author: windows-driver-content
description: TBD.
old-location: display\d3dkmt-set-colorspace-transform.htm
old-project: display
ms.assetid: 253c689d-ce30-4065-920a-030e3e9f3b8e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_SET_COLORSPACE_TRANSFORM, D3DKMT_SET_COLORSPACE_TRANSFORM structure [Display Devices], _D3DKMT_SET_COLORSPACE_TRANSFORM, d3dkmthk/D3DKMT_SET_COLORSPACE_TRANSFORM, display.d3dkmt-set-colorspace-transform
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
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
-	d3dkmthk.h
api_name:
-	D3DKMT_SET_COLORSPACE_TRANSFORM
product: Windows
targetos: Windows
req.typenames: D3DKMT_SET_COLORSPACE_TRANSFORM
---

# _D3DKMT_SET_COLORSPACE_TRANSFORM structure
TBD

## Syntax
```
typedef struct _D3DKMT_SET_COLORSPACE_TRANSFORM {
  LUID                           AdapterLuid;
  D3DDDI_VIDEO_PRESENT_TARGET_ID VidPnTargetId;
  D3DDDI_GAMMARAMP_TYPE          Type;
  UINT                           Size;
  union {
    D3DKMDT_3x4_COLORSPACE_TRANSFORM *pColorSpaceTransform;
  };
} D3DKMT_SET_COLORSPACE_TRANSFORM;
```

## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmthk.h |