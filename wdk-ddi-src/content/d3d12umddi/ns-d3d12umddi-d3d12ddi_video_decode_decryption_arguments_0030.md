---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030
title: D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030
author: windows-driver-content
description: Video decode decryption arguments.
old-location: display\d3d12ddi-video-decode-decryption-arguments-0030.htm
old-project: display
ms.assetid: cdd89f48-1b27-4362-81b3-ed3b89b80b6e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030, D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030, display.d3d12ddi-video-decode-decryption-arguments-0030
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
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
-	d3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030
---

# D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030 structure
Video decode decryption arguments.

## Syntax
````
typedef struct _D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030 {
  D3D12DDI_HCRYPTOSESSIONPOLICY_0030  hDrvCryptoSessionPolicy;
  CONST VOID *                        pIV;
  UINT                                IVSize;
  CONST VOID *                        pSubSampleMappingBlock;
  UINT                                SubSampleMappingCount;
} D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030, D3D12DDI_VIDEO_DECODE_DECRYPTION_ARGUMENTS_0030;
````

## Members


`hDrvCryptoSessionPolicy`

Crypto session policy.

`IVSize`

Initialization vector size.

`pIV`

Initialization vector.

`pSubSampleMappingBlock`

Sub sample mapping block.

`SubSampleMappingCount`

Sub sample mapping count.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h |