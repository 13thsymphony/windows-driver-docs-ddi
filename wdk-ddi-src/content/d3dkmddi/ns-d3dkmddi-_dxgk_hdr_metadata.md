---
UID: NS:d3dkmddi._DXGK_HDR_METADATA
title: "_DXGK_HDR_METADATA"
author: windows-driver-content
description: Contains information about the HDR metadata.
old-location: display\dxgk_hdr_metadata.htm
old-project: display
ms.assetid: 15AE3B05-1FD4-4ADB-B92F-9098225A920B
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGK_HDR_METADATA, DXGK_HDR_METADATA structure [Display Devices], _DXGK_HDR_METADATA, d3dkmddi/DXGK_HDR_METADATA, display.dxgk_hdr_metadata
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
-	DXGK_HDR_METADATA
product: Windows
targetos: Windows
req.typenames: DXGK_HDR_METADATA
---

# _DXGK_HDR_METADATA structure
Contains information about the HDR metadata.

## Syntax
````
typedef struct _DXGK_HDR_METADATA {
  D3DDDI_HDR_METADATA_TYPE  Type;
  UINT                      Size;
  VOID                      *pMetaData;
} DXGK_HDR_METADATA;
````

## Members


`pMetaData`

Pointer to the HDR metadata.

`Size`

Indicates the size of the HDR metadata.

`Type`

Indicates the type of the HDR metadata.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmddi.h |