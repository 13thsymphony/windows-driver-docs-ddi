---
UID: NS:d3dkmthk._D3DKMT_CREATESTANDARDALLOCATIONFLAGS
title: "_D3DKMT_CREATESTANDARDALLOCATIONFLAGS"
author: windows-driver-content
description: Used to create standard allocation flags.
old-location: display\d3dkmt-createstandardallocationflags.htm
old-project: display
ms.assetid: a1a4aa0c-2edc-48b9-ad49-c876be930955
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMT_CREATESTANDARDALLOCATIONFLAGS, D3DKMT_CREATESTANDARDALLOCATIONFLAGS structure [Display Devices], _D3DKMT_CREATESTANDARDALLOCATIONFLAGS, d3dkmthk/D3DKMT_CREATESTANDARDALLOCATIONFLAGS, display.d3dkmt-createstandardallocationflags
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
-	D3DKMT_CREATESTANDARDALLOCATIONFLAGS
product: Windows
targetos: Windows
req.typenames: D3DKMT_CREATESTANDARDALLOCATIONFLAGS
---

# _D3DKMT_CREATESTANDARDALLOCATIONFLAGS structure
Used to create standard allocation flags.

## Syntax
````
typedef struct _D3DKMT_CREATESTANDARDALLOCATIONFLAGS {
  union {
    struct {
      UINT Reserved  :32;
    };
    UINT Value;
  };
} D3DKMT_CREATESTANDARDALLOCATIONFLAGS;
````

## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmthk.h |