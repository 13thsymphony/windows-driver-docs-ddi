---
UID: NS:d3dkmthk._D3DKMT_CREATEBUNDLEOBJECT
title: "_D3DKMT_CREATEBUNDLEOBJECT"
author: windows-driver-content
description: Holds information to create a bundle object.
old-location: display\d3dkmt-createbundleobject.htm
old-project: display
ms.assetid: dbb01112-9d28-4dbf-88c7-3304d9d6a661
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_CREATEBUNDLEOBJECT, D3DKMT_CREATEBUNDLEOBJECT structure [Display Devices], _D3DKMT_CREATEBUNDLEOBJECT, d3dkmthk/D3DKMT_CREATEBUNDLEOBJECT, display.d3dkmt-createbundleobject
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
-	D3DKMT_CREATEBUNDLEOBJECT
product: Windows
targetos: Windows
req.typenames: D3DKMT_CREATEBUNDLEOBJECT
---

# _D3DKMT_CREATEBUNDLEOBJECT structure
Holds information to create a bundle object.

## Syntax
```
typedef struct _D3DKMT_CREATEBUNDLEOBJECT {
  UINT                cObjects;
  CONST D3DKMT_HANDLE *phObjects;
  POBJECT_ATTRIBUTES  *ppObjectAttributes;
  POBJECT_ATTRIBUTES  pBundleObjectAttributes;
  DWORD               dwBundleDesiredAccess;
  HANDLE              hNtBundleHandle;
} D3DKMT_CREATEBUNDLEOBJECT;
```

## Members


`cObjects`

The number of the DXGK object to be bundled.

`phObjects`

A pointer to the array of the DXGK object to be bundled.

`ppObjectAttributes`

An array of pointers to object attributes for DXGK objects.

`pBundleObjectAttributes`

Object attributes for the bundled object.

`dwBundleDesiredAccess`

The desired access for bundle handle.

`hNtBundleHandle`

The NT bundle handle.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmthk.h |