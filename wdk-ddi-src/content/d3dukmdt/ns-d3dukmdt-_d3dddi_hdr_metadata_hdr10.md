---
UID: NS:d3dukmdt._D3DDDI_HDR_METADATA_HDR10
title: "_D3DDDI_HDR_METADATA_HDR10"
author: windows-driver-content
description: Describes the metadata for HDR10.
old-location: display\d3dddi_hdr_metadata_hdr10.htm
old-project: display
ms.assetid: F7316327-C860-4138-A19B-3326CE9210C0
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: D3DDDI_HDR_METADATA_HDR10 structure [Display Devices], display.d3dddi_hdr_metadata_hdr10, D3DDDI_HDR_METADATA_HDR10, _D3DDDI_HDR_METADATA_HDR10, d3dukmdt/D3DDDI_HDR_METADATA_HDR10
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dukmdt.h
apiname:
-	D3DDDI_HDR_METADATA_HDR10
product: Windows
targetos: Windows
req.typenames: D3DDDI_HDR_METADATA_HDR10
---

# _D3DDDI_HDR_METADATA_HDR10 structure
Describes the metadata for HDR10.

## Syntax
````
typedef struct _D3DDDI_HDR_METADATA_HDR10 {
  UINT16 RedPrimary[2];
  UINT16 GreenPrimary[2];
  UINT16 BluePrimary[2];
  UINT   MaxMasteringLuminance;
  UINT   MinMasteringLuminance;
  UINT16 MaxContentLightLevel;
  UINT16 MaxFrameAverageLightLevel;
} D3DDDI_HDR_METADATA_HDR10;
````

## Members


`BluePrimary`

The chromaticity coordinates of the 1.0 blue value. Index 0 contains the X coordinate and index 1 contains the Y coordinate.

`GreenPrimary`

The chromaticity coordinates of the 1.0 green value. Index 0 contains the X coordinate and index 1 contains the Y coordinate.

`MaxContentLightLevel`

The maximum nit value used anywhere in the content.

`MaxFrameAverageLightLevel`

The per-frame average of the maximum nit values.

`MaxMasteringLuminance`

The maximum number of nits of the display used to master the content.

`MinMasteringLuminance`

The minimum number of nits of the display used to master the content.

`RedPrimary`

The chromaticity coordinates of the 1.0 red value. Index 0 contains the X coordinate and index 1 contains the Y coordinate.

`WhitePoint`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dukmdt.h |