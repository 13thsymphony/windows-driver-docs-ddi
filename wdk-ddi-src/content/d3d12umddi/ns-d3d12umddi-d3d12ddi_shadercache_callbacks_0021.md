---
UID: NS:d3d12umddi.D3D12DDI_SHADERCACHE_CALLBACKS_0021
title: D3D12DDI_SHADERCACHE_CALLBACKS_0021
author: windows-driver-content
description: Specifies shader cache callback functions.
old-location: display\d3d12ddi_shadercache_callbacks_0021.htm
old-project: display
ms.assetid: EBA976B0-3B44-4482-B1B0-31A84150C056
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDI_SHADERCACHE_CALLBACKS_0021, D3D12DDI_SHADERCACHE_CALLBACKS_0021 structure [Display Devices], d3d12umddi/D3D12DDI_SHADERCACHE_CALLBACKS_0021, display.d3d12ddi_shadercache_callbacks_0021
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
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
-	D3d12umddi.h
api_name:
-	D3D12DDI_SHADERCACHE_CALLBACKS_0021
product:
- Windows
targetos: Windows
req.typenames: D3D12DDI_SHADERCACHE_CALLBACKS_0021
---

# D3D12DDI_SHADERCACHE_CALLBACKS_0021 structure
Specifies shader cache callback functions.

## Syntax
```
typedef struct D3D12DDI_SHADERCACHE_CALLBACKS_0021 {
  PFND3D12DDI_SHADERCACHEGETVALUE_CB_0021   pfnShaderCacheGetValueCb;
  PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021 pfnShaderCacheStoreValueCb;
};
```

## Members


`pfnShaderCacheGetValueCb`

A callback function that gets a shader cache value.

`pfnShaderCacheStoreValueCb`

A callback function that stores a shader cache value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |