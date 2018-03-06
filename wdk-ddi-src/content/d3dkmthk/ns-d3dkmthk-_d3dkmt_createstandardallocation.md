---
UID: NS:d3dkmthk._D3DKMT_CREATESTANDARDALLOCATION
title: "_D3DKMT_CREATESTANDARDALLOCATION"
author: windows-driver-content
description: Used to create a standard allocation.
old-location: display\d3dkmt-createstandardallocation.htm
old-project: display
ms.assetid: 7698ab93-68af-479d-97a4-c45ac84b0710
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_CREATESTANDARDALLOCATION, D3DKMT_CREATESTANDARDALLOCATION structure [Display Devices], _D3DKMT_CREATESTANDARDALLOCATION, d3dkmthk/D3DKMT_CREATESTANDARDALLOCATION, display.d3dkmt-createstandardallocation
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
-	D3DKMT_CREATESTANDARDALLOCATION
product: Windows
targetos: Windows
req.typenames: D3DKMT_CREATESTANDARDALLOCATION
---

# _D3DKMT_CREATESTANDARDALLOCATION structure
Used to create a standard allocation.

## Syntax
````
typedef struct _D3DKMT_CREATESTANDARDALLOCATION {
  D3DKMT_STANDARDALLOCATIONTYPE        Type;
  union {
    D3DKMT_STANDARDALLOCATION_EXISTINGHEAP ExistingHeapData;
  };
  D3DKMT_CREATESTANDARDALLOCATIONFLAGS Flags;
} D3DKMT_CREATESTANDARDALLOCATION;
````

## Members


`Flags`

Holds the flags needed to create a standard allocation.

`Type`

The type of the standard allocation.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmthk.h |