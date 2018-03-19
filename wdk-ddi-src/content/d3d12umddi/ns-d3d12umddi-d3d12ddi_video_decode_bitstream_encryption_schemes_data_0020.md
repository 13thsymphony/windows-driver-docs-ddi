---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEMES_DATA_0020
title: D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEMES_DATA_0020
author: windows-driver-content
description: Specifies information used to retrieve the bitstream encryption schemes supported for a decode profile.
old-location: display\d3d12ddi_video_decode_bitstream_encryption_schemes_data_0010.htm
old-project: display
ms.assetid: A028463A-5914-4522-8683-F0A692CF09A3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEMES_DATA_0020, D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEMES_DATA_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEMES_DATA_0020, display.d3d12ddi_video_decode_bitstream_encryption_schemes_data_0010
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
-	D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEMES_DATA_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEMES_DATA_0020
---

# D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEMES_DATA_0020 structure
Specifies information used to retrieve the bitstream encryption schemes supported for a decode profile.

## Syntax
````
typedef struct D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEMES_DATA_0020 {
  UINT    NodeIndex;
  REFGUID DecodeProfile;
  UINT    EncryptionSchemeCount;
  GUID    *pEncryptionSchemes;
} D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEMES_DATA_0020;
````

## Members


`NodeIndex`

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to.

`DecodeProfile`

The decode profile to retrieve bitstream encryption schemes for.

`EncryptionSchemeCount`

The number of schemes to retrieve.  The runtime ensures this value matches the value returned from PFND3D12DDI_VIDEO_GETCAPS with D3D12DDI_CAPSTYPE_VIDEO set to D3D12DDICAPS_TYPE_VIDEO_DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT.

`pEncryptionSchemes`

A pointer to a list of supported encryption schemes.  The calling application allocates storage for the list before it calls the <a href="https://msdn.microsoft.com/2E986E37-30C7-45FE-BC8B-A6DD5670938F">CheckFeatureSupport</a> method.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/2E986E37-30C7-45FE-BC8B-A6DD5670938F">CheckFeatureSupport</a>



<a href="..\d3d12umddi\nc-d3d12umddi-pfnd3d12ddi_video_get_bitstream_encryption_scheme_count_0020.md">pfnGetBitstreamEncryptionSchemeCount</a>