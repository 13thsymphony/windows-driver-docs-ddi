---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_CRYPTO_SESSION_TRANSFORM_SUPPORT_DATA_0030
title: D3D12DDI_VIDEO_CRYPTO_SESSION_TRANSFORM_SUPPORT_DATA_0030
author: windows-driver-content
description: Video crypto session transform support data.
old-location: display\d3d12ddi-video-crypto-session-transform-support-data-0030.htm
old-project: display
ms.assetid: fb83a03e-56d9-4daf-93c1-407744ad134a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDI_VIDEO_CRYPTO_SESSION_TRANSFORM_SUPPORT_DATA_0030, D3D12DDI_VIDEO_CRYPTO_SESSION_TRANSFORM_SUPPORT_DATA_0030 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_CRYPTO_SESSION_TRANSFORM_SUPPORT_DATA_0030, display.d3d12ddi-video-crypto-session-transform-support-data-0030
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
-	D3D12DDI_VIDEO_CRYPTO_SESSION_TRANSFORM_SUPPORT_DATA_0030
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_CRYPTO_SESSION_TRANSFORM_SUPPORT_DATA_0030
---

# D3D12DDI_VIDEO_CRYPTO_SESSION_TRANSFORM_SUPPORT_DATA_0030 structure
Video crypto session transform support data.

## Syntax
```
typedef struct D3D12DDI_VIDEO_CRYPTO_SESSION_TRANSFORM_SUPPORT_DATA_0030 {
  UINT                                                 NodeIndex;
  GUID                                                 DecodeProfile;
  GUID                                                 ContentProtectionSystem;
  D3D12DDI_CRYPTO_SESSION_FLAGS_0030                   Flags;
  D3D12DDI_BITSTREAM_ENCRYPTION_TYPE_0030              BitstreamEncryption;
  D3D12DDI_CRYPTO_SESSION_TRANSFORM_OPERATION_0030     Operation;
  BOOL                                                 ProtectedOutputRequired;
  UINT64                                               InputAlignment;
  UINT64                                               InputPreambleSize;
  UINT64                                               OutputAlignment;
  UINT64                                               OutputPreambleSize;
  D3D12DDI_CRYPTO_SESSION_TRANSFORM_SUPPORT_FLAGS_0030 Support;
};
```

## Members


`NodeIndex`

Node index.

`DecodeProfile`

Decode profile.

`ContentProtectionSystem`

Content protection system.

`Flags`

Flags.

`BitstreamEncryption`

Bitstream encryption.

`Operation`

Operation.

`ProtectedOutputRequired`

Protected output required.

`InputAlignment`

Input alignment.

`InputPreambleSize`

Input preamble size.

`OutputAlignment`

Output alignment.

`OutputPreambleSize`

Output preamble size.

`Support`

Support.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h |